# iOS-cheat-sheet
This is an iOS Programming Cheat Sheet for a quick developers reference for the syntax verification. Syntax programming languages include Swift and Objective C.

## String

#### Objective C

```
[string length] == 0 
```

#### Swift

#### Initializations
```
var stringArray = [String]()
```

##### Non-Optional
```
let myString: String = ""

if myString.isEmpty {
    print("String is empty.")
    return 
}

```
##### Optional

```
let myOptionalString: String? = nil

guard let myString = myOptionalString, !myString.isEmpty else {
    print("String is nil or empty.")
    return
}
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
numbers.sorted { $0 < $1 } // Ascending     -> output   : [7, 12, 19, 20] 
numbers.sorted { $0 > $1 } // Descending    -> output   : [20, 19, 12, 7]
```
##### Map
Returns an array containing the results of mapping the given closure over the sequence's elements.
```
var numbers = [20, 19, 7, 12]
let cast = ["Vivien", "Marlon", "Kim", "Karl"]
print(cast.map { $0.lowercased() })     // Lower cased  -> output : ["vivien", "marlon", "kim", "karl"]
print(cast.map { $0.count })            // Count        -> output : [6, 6, 3, 4] 
print(cast.sorted {$0.count < $1.count})// Ascending based on count -> output : ["Kim", "Karl", "Vivien", "Marlon"]
```
