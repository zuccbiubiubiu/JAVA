# 面向对象编程
## 静态内部类、非静态内部类、内部类、外部类的辨析
- 外部类是房子（house），他是最大的，包含了内部类
- 内部类是房间（room）,他隶属于外部类
- 静态内部类，是是房子的设计图，他不依赖房子，想看设计图，不需要真的建一个房子，然后才能看设计图（还是有问题吧 但也想不出更好的比喻）
- 非静态内部类，是房间的家具，依赖房子
### 具体实例
>非静态类例子
```java
public class House {
    private String houseName = "My House";

    public class Room {
        public void showHouseName() {
            // 房间可以访问房子的名字
            System.out.println(houseName);
        }
    }

    public static void main(String[] args) {
        House myHouse = new House(); // 创建一个房子
        Room myRoom = myHouse.new Room(); // 在房子里创建一个房间
        myRoom.showHouseName(); // 输出: My House
    }
}
```
>静态类例子
```java
public class House {
    private static String design = "House Design";

    public static class Design {
        public void showDesign() {
            // 设计图可以访问房子的设计信息
            System.out.println(design);
        }
    }

    public static void main(String[] args) {
        Design houseDesign = new Design(); // 直接创建设计图
        houseDesign.showDesign(); // 输出: House Design
    }
}

```
