# Homework 4(Week 3)
```
/*
Course: DGL 204 - Programming for mobile app development
Author: Ashley Blacquiere

Week 3 content, including interfaces
*/


abstract class ServiceStation(
    val priceOfGasPerLitre: Double = 2.3
) {

}

interface Pumpable {
    fun pumpGas(fundsProvided: Double)
}

interface Payable {
    fun acceptPayment(fundsProvided: Double)
}
//Interface Fillable
interface Fillable {
    fun fillTank(station: ShellStation)
}
//Interface Driveable
interface Driveable {
    fun accelerate(station: Vehicle)
    fun brake(station: Vehicle)

}

class ShellStation(
    val name: String = "Shell Station"
) : ServiceStation(), Pumpable, Payable {
    override fun pumpGas(fundsProvided: Double) {
        val litersOfGas = fundsProvided / priceOfGasPerLitre
        println("Filling the tank to $litersOfGas litres")
    }

    override fun acceptPayment(fundsProvided: Double) {
        println("Total Payment: $fundsProvided")//Implement acceptPayment method
    }
}

open class Vehicle(
    val cashAvailable: Double = 10.0
) {
    open fun fillTank(station: ShellStation) {
        station.pumpGas(cashAvailable)
    }
}
//Car Class
class Car(
    val topSpeed: Double = 200.0

) : Vehicle(),Fillable,Driveable {
    override fun fillTank(station: ShellStation) {
        station.pumpGas(cashAvailable)
    }


    override fun accelerate(station: Vehicle) {
        println("Topspeed: $topSpeed")
    }

    override fun brake(station: Vehicle) {
        println("Brake")
    }

}


fun main() {

    val s = ShellStation()
    val c = Car()
    c.fillTank(s)
    s.acceptPayment(fundsProvided = 30.0)



}
```
# Reflection Regarding Homework 4
I enjoyed to complete this assignment as I have learned so many new lessons regarding Kotlin. I think I changed the code as per requirments of the assignment. First, I created two interfaces
```
//Interface Fillable
interface Fillable {
    fun fillTank(station: ShellStation)
}
//Interface Driveable
interface Driveable {
    fun accelerate(station: Vehicle)
    fun brake(station: Vehicle)

}
```
Afterwards, I designed the class **Car** as per the requirments of the assignment
```
//Car Class
class Car(
    val topSpeed: Double = 200.0

) : Vehicle(),Fillable,Driveable {
    override fun fillTank(station: ShellStation) {
        station.pumpGas(cashAvailable)
    }


    override fun accelerate(station: Vehicle) {
        println("Topspeed: $topSpeed")
    }

    override fun brake(station: Vehicle) {
        println("Brake")
    }

}
```
I also implemented the *acceptpayment* method 
```
override fun acceptPayment(fundsProvided: Double) {
        println("Total Payment: $fundsProvided")//Implement acceptPayment method
    }
```
While I was going through the assignments, I also had been watching the week 3 videos over and over again as well as I visited [W3 website](https://www.w3schools.com/kotlin/kotlin_intro.php) for some help. I only used our Brightspace video tutorials and [W3 website](https://www.w3schools.com/kotlin/kotlin_intro.php) for my resources. Overall the assignment was a moderate assignment that means neither too easy nor too difficult. In my opinion, if more mathematical calculations could be added to our reference example then it would be more helpful.
