#Kotlin oop with code practice



##Parameterized and default  constructor

class Person(val name: String = "Unknown", val age: Int = 0) {
    fun greet() {
        println("Hello, my name is $name and I am $age years old.")
    }
}

fun main() {
    val person1 = Person("Alice", 25) // Parameterized
    val person2 = Person()            // Default

    person1.greet()
    person2.greet()
}


##Encapsulation 


class Student {
    private var grade: Int = 0

    fun setGrade(g: Int) {
        if (g in 0..100) grade = g
        else println("Invalid grade!")
    }

    fun getGrade(): Int {
        return grade
    }
}

fun main() {
    val s = Student()
    s.setGrade(85)
    println("Grade: ${s.getGrade()}")
    s.setGrade(150)  // Invalid
}


##Inheritence

open class Animal {
    open fun makeSound() {
        println("Animal makes a sound")
    }
}

class Dog : Animal() {
    override fun makeSound() {
        println("Dog barks")
    }
}

fun main() {
    val a = Animal()
    val d = Dog()
    a.makeSound()
    d.makeSound()
}


##Polyorphism 

##Function override

open class Shape {
    open fun draw() {
        println("Drawing a shape")
    }
}

class Circle : Shape() {
    override fun draw() {
        println("Drawing a circle")
    }
}

class Square : Shape() {
    override fun draw() {
        println("Drawing a square")
    }
}

fun main() {
    val shape1 = Shape()
    val shape2 = Circle()
    val shape3 = Square()

    shape1.draw()  // Output: Drawing a shape
    shape2.draw()  // Output: Drawing a circle
    shape3.draw()  // Output: Drawing a square
}


##Function overload

class Calculator {
    fun add(a: Int, b: Int): Int {
        return a + b
    }

    fun add(a: Double, b: Double): Double {
        return a + b
    }

    fun add(a: Int, b: Int, c: Int): Int {
        return a + b + c
    }
}

fun main() {
    val calc = Calculator()
    println(calc.add(2, 3))
    println(calc.add(2.5, 3.6))
    println(calc.add(1, 2, 3))
}


##Abstraction

abstract class Appliance {
    abstract fun turnOn()
    abstract fun turnOff()

    fun plugIn() {
        println("Appliance plugged in")
    }
}

class Fan : Appliance() {
    override fun turnOn() {
        println("Fan is on")
    }

    override fun turnOff() {
        println("Fan is off")
    }
}

fun main() {
    val fan = Fan()
    fan.plugIn()
    fan.turnOn()
    fan.turnOff()
}

##Multiple Interface

interface Engine {
    fun startEngine()
}

interface MusicPlayer {
    fun playMusic()
}

class Car : Engine, MusicPlayer {
    override fun startEngine() {
        println("Engine started")
    }

    override fun playMusic() {
        println("Playing music")
    }
}

fun main() {
    val myCar = Car()
    myCar.startEngine()
    myCar.playMusic()
}


