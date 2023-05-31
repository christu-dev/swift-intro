# swift-intro
Introduction to Xcode, Swift, Playgrounds environment, immutable and mutable variables, basic data types, classes, structs, inheritance, constructors, initializers, scope, reference, postfix string concat, if statements, switch statements, enum, enum iteration

Playground file can be opened using Xcode, code is included below for convenience and viewing purposes
# chris_firstPlayground.playground
import UIKit

var greeting = "Hello, playground"
var age = 30
print(age)

let myName = "Chris"

print(myName)

age = 21
print(age)

//classes and subclasses
class Car {
    let make: String
    let model: String
    let year: Int
    func honkHorn(){
        print("Beep.")
    }
    init(make: String, model: String, year: Int){
        self.make = make
        self.model = model
        self.year = year
        
    }
}
let myFirst = Car(make: "Toyota", model: "RAV4", year: 2021)
print("Make: ", myFirst.make , "Model: " , myFirst.model, "Year: ", myFirst.year)

let hisFirst = myFirst
print(hisFirst.model)

class clownCar: Car {
    var clownNumber: Int
    
    func newhonkHorn(){
        print ("Beep beep, huahuahuahua!")
    }
    init(make: String, model: String, year: Int, clownNumber: Int) {
        self.clownNumber = clownNumber
        super.init(make: make, model: model, year: year)
    }
    
}

let myFirstClownCar = clownCar(make: "BMW",model:"i5",year:2005,clownNumber: 4)

print(myFirstClownCar.clownNumber)
myFirstClownCar.clownNumber = 5
print(myFirstClownCar.clownNumber)
print(myFirstClownCar.model)


//Structs
struct NewCar {
    let make:String
    let model:String
    var miles: Double
}
var thisCar = NewCar(make: "Honda", model: "Pilot", miles: 900.5)
print(thisCar.model)
var thatCar = thisCar
print(thatCar.miles)
thatCar.miles = 969.5

print(thisCar.miles)
print(thatCar.miles)

//functions
myFirstClownCar.newhonkHorn()
myFirst.honkHorn()
myFirstClownCar.honkHorn()


func calcProduct(x: Double, y:Double) -> Double {
    return x * y
}

let result = calcProduct(x:4.3, y:5.5)
print(result)


//if statement
myFirstClownCar.clownNumber = 10 //comment this out to change the if statement

if myFirstClownCar.clownNumber == 10 {
    print("We hit 10 clowns!")
}
else {
    print("We currently do not have exactly 10 clowns!")
}

//switch statement
var myCharacter : Character = "b" //change this value to check the switch statement
//myCharacter = "j"
//myCharacter = "b"
myCharacter = "x"
switch myCharacter{
case "j":
        print("Congrats, the character is j.")
case "b":
        print("Okay, the character is b.")
default:
        print("That wasn't it,", myCharacter, "isn't a letter we care about.")
}
//enums

enum Seasons: String {
    case summer = "☀️"
    case spring = "🌹"
    case fall = "🍂"
    case winter = "☃️"
}

print(Seasons.summer)
print(Seasons.summer.rawValue)

let favoriteSeasons: [Seasons] = [.summer, .fall]
//print(favoriteSeasons)

for season in favoriteSeasons {
    print(season.rawValue)
}


