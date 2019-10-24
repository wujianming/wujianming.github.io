---
title: Gale-Shapley algorithm求最好的婚姻匹配
layout: post
categories:
- 算法
tags: 算法
---

## 问题

设4男4女，他们各自对异性的钟情程度如下表：

<style>
table th:first-of-type {
	width: 100px;
}
</style>

**男** | **钟情女子**（钟情程度按顺序严格递减）
:---|:---
Man1|Woman1、Woman2、Woman3、Woman4
Man2|Woman1、Woman3、Woman2、Woman4
Man3|Woman3、Woman2、Woman1、Woman4
Man4|Woman4、Woman2、Woman1、Woman3

**女子** | **暗恋男子**（暗恋程度按顺序严格递减）
:---|:---
Woman1|Man2、Man1、Man3、Man4
Woman2|Man1、Man3、Man2、Man4
Woman3|Man3、Man4、Man2、Man1
Woman4|Man3、Man1、Man2、Man4

试给出最好的婚姻匹配。

## 算法

- **第一轮** 先让所有男子向自己最钟情的女子求婚，然后让所有女子挑选最中意的，并剔除所有其他人。
- **第二轮** 让没有被选中的男子再次向自己第二钟情的女子求婚，然后让所有女子挑选最中意的，并剔除所有其他人。  
- **第三轮** 重复第二轮，直到所有人找到配偶为止。


## 实验过程

```Java
import java.util.*;
import java.io.*;
import java.io.IOException;

/**
 * @author wujianming
 */
public class StableMatching {

    List<String> men =  null;
    List<String> women = null;
    Map<String, List<String>> menRanking = null;
    Map<String, List<String>> womenRanking = null;

    public static void main(String[] args) {
        new StableMatching(StableMatching.class.getClassLoader()
                .getResource("data.txt").getFile());

    }

    public StableMatching(String filePath) {
        BufferedReader fileReader = null;

        men = new ArrayList<String>();
        women = new ArrayList<String>();
        menRanking = new HashMap<String, List<String>>();
        womenRanking = new HashMap<String, List<String>>();

        try {
            String currentLineString = null;
            String[] currentLineArray = null;
            fileReader = new BufferedReader(new FileReader(filePath));

            while ((currentLineString = fileReader.readLine()) != null) {
                currentLineArray = currentLineString.split(" ");
                int numberOfPeople = currentLineArray.length - 1;
                String ranker = currentLineArray[0];
                List<String> prefList = Arrays.asList(Arrays.copyOfRange(currentLineArray, 1, currentLineArray.length));
                if (women.size() == 0) {
                    women.addAll(prefList);
                }

                boolean isWoman = false;

                for (String currentWoman : women) {
                    if (ranker.equals(currentWoman)) {
                        isWoman = true;
                    }
                }
                if (isWoman == false) {
                    men.add(ranker);
                    menRanking.put(ranker, prefList);
                } else {
                    womenRanking.put(ranker, prefList);
                }
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (fileReader != null) {
                    fileReader.close();
                    Map<String, String> matches = doMatching();
                    for (Map.Entry<String, String> matching : matches.entrySet()) {
                        System.out.println(matching.getKey() + " " + matching.getValue());
                    }
                }
            } catch (IOException ex) {
                ex.printStackTrace();
            }
        }
    }

    private Map<String, String> doMatching() {
        Map<String, String> matches = new TreeMap<String, String>();
        List<String> freeMen = new LinkedList<String>();
        freeMen.addAll(men);
        while (!freeMen.isEmpty()) {
            String currentMan = freeMen.remove(0);
            List<String> currentManPrefers = menRanking.get(currentMan);

            for (String woman : currentManPrefers) {
                if (matches.get(woman) == null) {
                    matches.put(woman, currentMan);
                    break;
                } else {
                    String otherMan = matches.get(woman);
                    List<String> currentWomanRanking = womenRanking.get(woman);
                    if (currentWomanRanking.indexOf(currentMan) < currentWomanRanking.indexOf(otherMan)) {
                        matches.put(woman, currentMan);
                        freeMen.add(otherMan);
                        break;
                    }
                }
            }
        }
        return matches;
    }
}
```

下为输入数据。

```data.txt
Man1 Woman1 Woman2 Woman3 Woman4
Man2 Woman1 Woman3 Woman2 Woman4
Man3 Woman3 Woman2 Woman1 Woman4
Man4 Woman4 Woman2 Woman1 Woman3
Woman1 Man2 Man1 Man3 Man4
Woman2 Man1 Man3 Man2 Man4
Woman3 Man3 Man4 Man2 Man1
Woman4 Man3 Man1 Man2 Man4
```

下为运行结果。

```plaintext
Woman1 Man2
Woman2 Man1
Woman3 Man3
Woman4 Man4
```


## 结论
1. 男子主动策略是男子的最佳策略
2. 男子主动策略是女子的最差策略

## 启示
- 爱要大胆一点。不论是男生还是女生，主动追求永远比被动等待更有希望获得幸福。

```
仔细想想这个算法，本质上就是将就：

1、男：就这么个恐龙！哎，比上不足，比下有余；
2、女：心仪的白马王子已经有主，这辈子就这命了，嫁鸡随鸡，嫁狗。
算法非常简单，但它却补充了“价高者得。”这一最基本的市场规律，因而对经济学产生了重要的意义。
```
