```java
Random ran =  new Random();
```
We usually use this expression to create a Random object.<br />In fact, a Random class has a constructor with parameters, you can pass an int parameter as a seed to it.<br />like this:
```java
Random ran = new Random(10);
```
<a name="PybdT"></a>
#### What does a seed mean in the Random class?
Actually, the constructor will set the current time as a seed if we evoke the constructor without any parameter. We can observe this from the source codes:

1. Constructor without parameter
```java
public Random() {
    setSeed(System.nanoTime() + seedBase);
    ++seedBase;
}
```

2. Constructor with parameters
```java
public Random(long seed) {
    setSeed(seed);
}
```
all evoke the setSeed method:
```java
public synchronized void setSeed(long seed) {
    this.seed = (seed ^ multiplier) & ((1L << 48) - 1);
    haveNextNextGaussian = false;
}
```
So we will know that the seed is a parameter to generate a random number.<br />The most important method in the Random class is the next(int) method, which uses the seed to calculate.
```java
protected synchronized int next(int bits) {
    seed = (seed * multiplier + 0xbL) & ((1L << 48) - 1);
    return (int) (seed >>> (48 - bits));
}
```
The seed will be assigned a new value every time it is calculated.<br />So the result value will be determined if you pass a fixed seed as a parameter to the constructor, as the calculation begins from this seed every time. The next value will be determined too, since the calculating progress is the same. So will be the third and fourth results, etc.<br />So that's why the value will be different when we use the constructor without any parameter to generate a random number because the current timestamp will be set as the seed, and the current timestamp will be different from each other every second.<br />Thus, the conclusion will be that the random number isn't relative to the state of the system, it will always be the same no matter where to evoke this random method with the same seed.<br />This characteristic can be used in the industry of research or lab since the result will always recur.
