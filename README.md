# iOS-cheat-sheet
This is an iOS Swift Programming Cheat Sheet for a quick reference for developers for the syntax verification.

#### Swift

#### Variables
```
var varInt = 42
var varFloat: Float = 2.034
var varSwift = "Godzilla"
var varDouble = 3.14159
let myString: String = ""
let myOptionalString: String? = nil
let width = 94
var stringArray = [String]()
```

#### View Controller

##### Comparing view controller
```
if(vc is UIViewController)
if(vc === viewController)
```

##### Sorting
```
var numbers = [20, 19, 7, 12]
let cast = ["Vivien", "Marlon", "Kim", "Karl"]
numbers.sorted { $0 < $1 }          // Ascending        -> output : [7, 12, 19, 20] 
numbers.sorted { $0 > $1 }          // Descending       -> output : [20, 19, 12, 7]
cast.sorted {$0.count < $1.count}   // Ascending(count) -> output : ["Kim", "Karl", "Vivien", "Marlon"]
```
##### Map [AppleDoc](https://developer.apple.com/documentation/swift/array/2908681-map) [LearnApp](https://learnappmaking.com/map-reduce-filter-swift-programming/)
Returns an array containing the results of mapping the given closure over the sequence's elements.
```
var numbers = [20, 19, 7, 12]
let cast = ["Vivien", "Marlon", "Kim1@", "Karl"]
cast.map { $0.lowercased() }        // Lower cased  -> output : ["vivien", "marlon", "kim1@", "karl"]
cast.map { $0.uppercased() }        // Upper cased  -> output : ["VIVIEN", "MARLON", "KIM1@", "KARL"]
cast.map { $0.count }               // Count        -> output : [6, 6, 5, 4]
cast.map({ number in number * 30 }) // Multiply     -> output : [600, 570, 210, 360]
```
