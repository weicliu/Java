# Java notes

## Upcasting and downcasting

By casting you are not actually changing the object itself, you are just labeling it differently. 

> For example, if you create a Cat and upcast it to Animal, then the object doesn't stop from being a Cat. It's still a Cat, but it's just treated as any other Animal and it's Cat properties are hidden until it's downcasted to a Cat again. 

## Compare Objects

- Think over to use `==` or `.equal()`

### Compare `Long`
- use `.equals()`
  - Use `x == null && y == null || x.equals(y)`
  - Long will cache the smaller value.

```java
public class MyClass {
    public static void main(String args[]) {
        Long x=10L;
        Long y=10L;
        
        Long a=10000000000L;
        Long b=10000000000L;

        System.out.println(x == y); // true
        System.out.println(x.equals(y)); // true
        
        System.out.println(a == b); // false
        System.out.println(a.equals(b)); // true
    }
}
```

## Serialization

### serialVersionUID

* `serialVersionUID` is needed when you implement Serializable interface, or JDK will generate one for you based on algorithm [here](https://docs.oracle.com/javase/8/docs/platform/serialization/spec/class.html#a4100).
* It will make sure that you use the same version to serialize and deserialize an object.
* You can use JDK's `serialver` to generate serialVersionUID for a class.

## Blocks

**Static Block**
* Executed only once: the first time you make an object or the first time you access the static member of that class
* Executed before constructor.

```java
class Test {
  static {
    ...
  }
}
```

**Initializer Block**
* Executed whenere you make an object, before constructor.
* Used to declaure/initialize the common part of various constructors of a class.

```java
public class Test {
  {
    ...
  }
}
```


## Others

- try/catch have different scope.
