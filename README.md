# iOS-cheat-sheet
This is an iOS Swift Programming Cheat Sheet for a quick reference for developers for the syntax verification.

#### Swift

#### Variables/Constants ([Type Annotation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Types.html)) ([Type Inference](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Types.html#//apple_ref/swift/grammar/type-inheritance-list))

```
// Variables

*** Type Annotation - The kind of values the variable can store  
var varFloat: Float = 2.034       -> Type Annotation 
var stringArray = [String]()      -> Type Annotation

*** Type Inference - Type inference enables a compiler to deduce the type of a particular expression automatically when it compiles your code, simply by examining the values you provide. 
var varInt = 42                   -> Type Inference 
var varSwift = "Godzilla"         -> Type Inference
var varDouble = 3.14159           -> Type Inference

// Constants
let width = 94
let myString: String = ""
let myOptionalString: String? = nil
let someArray: Array<String> = ["Alex", "Brian", "Dave"]
let someArray: [String] = ["Alex", "Brian", "Dave"]
```

#### Literals ([String](https://developer.apple.com/documentation/swift/expressiblebystringliteral))
```
// String : A string of characters which are enclosed in double quotes.
let word = "hello world"    ; print(word)         // String Literal                               -> output : "hello world" 
let ñ: Unicode.Scalar = "ñ" ; print(ñ)            // ExpressibleByUnicodeScalarLiteral            -> output : "ñ"
let snowflake: Character = "❄︎" ; print(snowflake) // ExpressibleByExtendedGraphemeClusterLiteral  -> output : "❄︎"

// Numerical 
Eg: 
var binaryNumber  = 0b1100             // Binary           -> output : 12  
var hexaNumber    = 0xC                // Hexa Decimal     -> output : 12 
var OctalNumber   = 0o14               // Octal Decimal    -> output : 12 

// Image
Eg:
#imageLiteral(resourceName: "Icon")

// Color
Eg:
#colorLiteral(red: 1, green: 1, blue: 1, alpha: 0.77)

```

#### View Controller

##### Comparing view controller
```
if(vc is UIViewController)
if(vc === viewController)
```

##### Sorting ([Sort](https://developer.apple.com/documentation/foundation/data/2292856-sort)) ([Sorted](https://developer.apple.com/documentation/foundation/data/2293440-sorted))
```
var numbers = [20, 19, 7, 12]
let cast = ["Vivien", "Marlon", "Kim", "Karl"]
numbers.sorted { $0 < $1 }          // Ascending        -> output : [7, 12, 19, 20] 
numbers.sorted { $0 > $1 }          // Descending       -> output : [20, 19, 12, 7]
cast.sorted {$0.count < $1.count}   // Ascending(count) -> output : ["Kim", "Karl", "Vivien", "Marlon"]
cast.sorted {$0.count > $1.count}   // Descending(count) -> output : ["Vivien", "Marlon", "Karl", "Kim"]
```
##### Map ([AppleDoc](https://developer.apple.com/documentation/swift/array/2908681-map)) ([LearnApp](https://learnappmaking.com/map-reduce-filter-swift-programming/))
Returns an array containing the results of mapping the given closure over the sequence's elements.
```
var numbers = [20, 19, 7, 12]
let cast = ["Vivien", "Marlon", "Kim1@", "Karl"]
cast.map { $0.lowercased() }        // Lower cased  -> output : ["vivien", "marlon", "kim1@", "karl"]
cast.map { $0.uppercased() }        // Upper cased  -> output : ["VIVIEN", "MARLON", "KIM1@", "KARL"]
cast.map { $0.count }               // Count        -> output : [6, 6, 5, 4]
cast.map({ number in number * 30 }) // Multiply     -> output : [600, 570, 210, 360]
```

##### Recursive Enumerations ([AppleDoc](https://docs.swift.org/swift-book/LanguageGuide/Enumerations.html))
A recursive enumeration is an enumeration that has another instance of the enumeration as the associated value for one or more of the enumeration cases. You indicate that an enumeration case is recursive by writing indirect before it, which tells the compiler to insert the necessary layer of indirection.
```
indirect enum ArithmeticNumbers {
    case number(Int)
    case addition(ArithmeticNumbers, ArithmeticNumbers)
    case multiplication(ArithmeticNumbers, ArithmeticNumbers)
}

func evaluate(_ expression: ArithmeticNumbers) -> Int {
    switch expression {
    case let .number(value):
        return value
    case let .addition(firstValue, secondValue):
        return evaluate(firstValue) + evaluate(secondValue)
    case let .multiplication(firstValue, secondValue):
        return evaluate(firstValue) * evaluate(secondValue)
    }
}

let num = ArithmeticNumbers.number(5)
print(num)

print(evaluate(ArithmeticNumbers.number(5)))

let addNums = evaluate(ArithmeticNumbers.addition(ArithmeticNumbers.number(5), ArithmeticNumbers.number(5)))
print(addNums)

let multi = evaluate(ArithmeticNumbers.multiplication(ArithmeticNumbers.number(5), ArithmeticNumbers.number(5)))
print(multi)

OUTPUT:
number(5)
5
10
25

```
