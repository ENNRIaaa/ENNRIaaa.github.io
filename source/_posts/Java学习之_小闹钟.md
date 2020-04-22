title: JavaSE自学之_小闹钟程序
date: 2018-04-13 19:08
toc: true



---

*2020年4月20日---这是前年自学JavaSE时写的，有些功能不会实现的时候就会找百度，后来因为自身原因学习也就搁置了。当初刚开始自学的时候，真是精神头十足，实现某种功能感觉特别有成就感。*

```java
import java.applet.Applet;
import java.applet.AudioClip;
import java.io.File;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;
import java.util.Timer;
import java.util.TimerTask;

/**
 * 这是一个简易的闹钟程序
 * 
 * @author liyan
 *
 */
public class Alarm {
    public static void main(String[] args) {
        HMS hms = new HMS();
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入闹铃响起的时间（时、分、秒）：");
        hms.h = sc.nextInt();
        hms.m = sc.nextInt();
        hms.s = sc.nextInt();
        timer(hms);
    }

    public static void getTime(HMS hms) throws Exception {
        SimpleDateFormat sdf = new SimpleDateFormat("HH:mm:ss");// 设置时间格式
        String time = sdf.format(new Date());// 用time接收字符串格式的系统时间
        System.out.println("当前时间为：" + time);
        String strArr[] = time.split(":");// 把字符串格式的时间按“时分秒”拆分并保存到数组strArr[]中
        if ((Integer.parseInt(strArr[0]) == hms.h) && (Integer.parseInt(strArr[1]) == hms.m)
                && (Integer.parseInt(strArr[2]) == hms.s)) {// 当系统时间与设定的响铃时间相同，执行方法体
            System.out.println("到点了");
            File file1 = new File("src\\wav\\tonghuazhen.wav");
            AudioClip sound1;
            sound1 = Applet.newAudioClip(file1.toURL());
            sound1.play();// 播放wav音频
        }
    }

    /*
     * 设置一个定时器timer,每隔1s调用一次getTime()
     */
    public static void timer(HMS hms) {
        Timer T = new Timer();
        T.schedule(new TimerTask() {

            @Override
            public void run() {
                try {
                    getTime(hms);
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        }, 0, 1000);
    }
}
```
```java
public class HMS {
    /**
     * 闹钟设定时间： 成员属性： 时：h 分：m 秒：s
     */
    int h;
    int m;
    int s;
}
```
以上就是我写的java简易闹钟程序的源代码，写得很简陋，但是我也已经尽力了