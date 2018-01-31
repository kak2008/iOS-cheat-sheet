# iOS-cheat-sheet
This is an iOS Programming Cheat Sheet for a quick developers reference for the syntax verification. Syntax programming languages include Swift and Objective C.

## String

#### Objective C

```
[string length] == 0 
```

#### Swift
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
