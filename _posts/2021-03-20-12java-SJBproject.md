# Java实现人机石头剪刀布

> 代码逻辑可能有不足之处，欢迎各位给出宝贵建议。

如标题所示，这期我tomatooo来整个活：用java实现人机石头剪刀布(简易版)，当个小小的练手项目，开搞——

```java
import java.util.Scanner;
import java.util.Arrays;
import java.util.List;//先导3个包

public class SJB {
    public static void main(String[] args) {
        maincode.game();//调用方法
    }
}

class maincode {
    public static void game() {
        System.out.print("你选择：");// 打印提示
        Scanner scan = new Scanner(System.in);
        String choice = scan.nextLine();// 获取输入
        List<String> list = Arrays.asList("石头", "剪刀", "布");
        int index = (int) (Math.random() * list.size());// 取随机值
        System.out.println(list.get(index));//打印随机值
        Scanner scann = new Scanner(System.in);
        System.out.println("再玩一局？1/2");//询问是否再玩一局
        int yn = scann.nextInt();
        if (yn == 1) {
            maincode.game();
        } else if (yn == 2) {
            System.out.println("结束");
        }
    }
}
```

