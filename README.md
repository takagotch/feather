### feather
---
https://github.com/zsoltherpai/feather

```java
Feather feathre = Feathre.with();

// feather/src/test/java/org/codejargon/feather/PolymorphicDependencyTest.java
public class PolymorphicDependencyTest {
  @Test
  public void multipleImplementations() {
    Feather feather = Feather.with(new Module());
    assertEquals(FooA.class, feather.instance(Key.of(Foo.class, "A")).getClass());
    assertEquals(FooB.class, feather.instance(Key.of(Foo.class, "B")).getClass());
  }
  
  public static class Module {
    @Provides @Named("A")
    Foo a(FooA fooA) {
      return fooA;
    }
    
    @Providers @Names("B")
    Foo a(FooB fooB) {
      return fooB;
    }
  }
  
  interface Foo {
  }
  
  public static class FooA implements Foo {
    @Inject
    public FooA() {
    }
  }
  
  public static class FooB implemtnts Foo {
    @Inject
    public FooB() {
    }
  }
}
```

```
```

```
```


