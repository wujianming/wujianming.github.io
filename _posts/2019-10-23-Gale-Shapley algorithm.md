---
title: Gale-Shapley algorithm求最好的婚姻匹配
layout: post
categories:
- 算法
tags: 算法
---

## 问题

设3男3女，他们各自对异性的钟情程度如下表
**男** | **钟情女子**（钟情程度按顺序严格递减）
---|---
Man1|Woman1、Woman2、Woman3、Woman4
Man2|Woman1、Woman3 Woman2 Woman4
Man3|Woman3、Woman2、Woman1、Woman4
Man4|Woman4、Woman2、Woman1、Woman3


**女子** | **暗恋男子**（暗恋程度按顺序严格递减）
---|---
Woman1|Man2、Man1、Man3、Man4
Woman2|Man1、Man3、Man2、Man4
Woman3|Man3、Man4、Man2、Man1
Woman4|Man3、Man1、Man2、Man4

试给出最好的婚姻匹配。

## 算法

- 第一轮 先让所有男子向自己最钟情的女子求婚，然后让所有女子挑选最中意的，并剔除所有其他人。
- 第二轮 让没有被选中的男子再次向自己第二钟情的女子求婚，然后让所有女子挑选最中意的，并剔除所有其他人。  
- 第三轮 重复第二轮，直到所有人找到配偶为止。


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

```plaintext
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
1. 男子主动策略是男子的最佳策略！
2. 男子主动策略是女子的最差策略！

## 启示
1. 先下手为强，后下手遭殃。
2. 务必学号数学

