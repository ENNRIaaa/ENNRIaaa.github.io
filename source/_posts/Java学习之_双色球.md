title: JavaSE自学之_双色球程序（随机数）
date: 2018-04-13 21:45
toc: true



---

*源代码：*

```java
package Thedoublechromosphere;

import java.util.ArrayList;
import java.util.Random;
import java.util.Set;
import java.util.TreeSet;

public class Demo {
    public static void main(String[] args) {
        Random random = new Random();// 实例化随机数对象
        Set<Object> set = new TreeSet<>();// 实例化Set对象，Set：无序，唯一
        System.out.println("“双色球”中奖号码为：");
        while (true) {
            int a = random.nextInt(32) + 1;// 整型变量a接收1-33随机数红球
            set.add(a);// 添加随机数到set中
            if (set.size() > 5) {
                System.out.print(set.toString());
                break;
            }
        }
        System.out.println(" " + (random.nextInt(15) + 1));// 生成1-16的随机数蓝球

        System.out.println("“排列五”中奖号码为：");

        ArrayList<Integer> arr = new ArrayList<Integer>();
        for (int i = 0; i < 5; i++) {
            arr.add(random.nextInt(9));
        }
        System.out.println(arr.toString());

    }
}
```