As a human instinct, you may think it will take the order from the son class to the parent class while searching for a method. It's simpler that if you find the method in the son class, you immediately evoke it, or continue to search from the parent class. If not found from both classes, report an error.   <br />Actually, it will create a space for both the son class and the parent class when you New an object, they will be stored in one. So in the polymorphism, you declare a parent class object by New an object of the son class, the parent class object will still point to the parent object in the heap. That's why you can only get a field in the parent class if you evoke the field that both exists in the parent and son classes.<br />So the process of evoking an overwrite method is: searching from the parent class in the heap, then to the area of methods, finding it has been overwritten, and at last evoking this overwritten method. So it appears that the parent class object can evoke the son class method, and that's why it will report an error when you evoke a method which exists in the son class but not in the parent class.

For example:
```java
class Animal{
    String name;
    public void eat(){
        System.out.println("Animal eat.");
    }
}
class Cat extends Animal{
    String name;
    @overwritte
    public void eat(){
        System.out.println("Cat eat.");
    }
}
public class Demo{
    public static void main(String[] args){
        Animal animal =  new Cat();
        animal.eat();
    }
}
```
![Java Heap_00.png](https://cdn.nlark.com/yuque/0/2024/png/47471281/1724399841280-f4c381ca-b4c1-45a4-bcc7-46c8f46c3a3b.png#averageHue=%2361bf68&clientId=u0d34ffb5-efaa-4&from=drop&id=u50e60bb7&originHeight=1247&originWidth=1859&originalType=binary&ratio=2&rotation=0&showTitle=false&size=90783&status=done&style=none&taskId=u6023ed42-4d01-4faf-a258-794758bd621&title=)
