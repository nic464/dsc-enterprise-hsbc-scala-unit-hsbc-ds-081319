
# `Unit`

* It can be invoked using `()`
* A `Unit` is analogous to void in Java, C, C++
* Used as an interpretation of not returning a something
* Another way to interpret `Unit` is that there is nothing to give

## About `Unit`


```scala
val x = ()
```




    x: Unit = ()
    



## `println` uses `Unit`

* There is a popular form of `Unit`
* It is called `println`
* `println` doesn’t return anything per se, but technically it returns `Unit`

Take a look at the signature of `Unit` at the following URL:

https://www.scala-lang.org/api/current/scala/Unit.html

Take a look at the signature of `println` at the following URL:

https://www.scala-lang.org/api/current/scala/Predef$.html

## Assigning `println`


```scala
println("Hello, Scala")
```

    Hello, Scala
    

Now assign to a value! Yes, you can!
The type of `h` will resolve to `Unit`


```scala
val h = println("Hello, Scala")
```

    Hello, Scala
    




    h: Unit = ()
    



### Where is `Unit` in the Scala hierarchy?

![anyanyvalanyrefunit.png](../images/anyanyvalanyrefunit.png)

## **Lab:** What is the return type of this?

**Step 1:** Without running, what do you think the return type is for the following?


```scala
def add(x: Int, y: Int) = {
  if (x > 10) println(x)
  else x + y
}
```




    add: (x: Int, y: Int)AnyVal
    



**Step 2:** Discuss the reasons why that returned what it did.

## `Unit` can be used anywhere

* `Unit` is just an object that represents void
* The following is a purely nonsensical method to prove that it can be treated like any object


```scala
def nonsense(g:Unit):Int = 50
```




    nonsense: (g: Unit)Int
    




```scala
nonsense(())
```




    res10: Int = 50
    



## Unplanned `Unit`

In methods, if you do not use the `=` that will implicitly mean that you are returning `Unit`

Given the following which is correct, this will add `x` and `y`:


```scala
def add(x:Int, y:Int) = {
   x + y
}
println(add(4,5))
```

    9
    




    add: (x: Int, y: Int)Int
    



If we didn’t use `=` here, this will implicitly return `Unit`


```scala
def badAdd(x: Int, y: Int) {
   x + y
}

println(badAdd(4, 5)) //Returns a ()!
```

    ()
    




    badAdd: (x: Int, y: Int)Unit
    



## Explicitly putting `Unit`

If we can to write out the `Unit` explicitly by stipulating `Unit` as the return type


```scala
def addUnit(x: Int, y: Int):Unit = {
   x + y
}
println(addUnit(4,5)) //Returns a ()!
```

    ()
    




    addUnit: (x: Int, y: Int)Unit
    



## Side Effects and `Unit`

* When seeing `Unit` in functional programming when being returned from a method, it means likely it is creating a side effect
* A side effect is when something is changed to the outside world either:
  * Printing to a screen
  * Printing to a printer
  * Saving to Storage
  * Changing State

The following is changing state. Notice that this is returning `Unit`!
Also, notice that there is `var` which is mutability!


```scala
var a = 0
def sideEffect() {
   a = a + 1
}
sideEffect()
```




    a: Int = 1
    sideEffect: ()Unit
    



## `Unit` Conclusion

* Unit won’t give you anything. (Those jerks)
* They are analogous to Java’s `void`.
* `Unit` are actually objects and not just a keyword like in Java
* `Unit` have a type, `Unit`
* Units have one value, `()`.
* Whenever you see a `()` that means you have a `Unit`.
