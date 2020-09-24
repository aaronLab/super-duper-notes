# Optional

About Optional

## How to declare

```swift
var myVar: String? = nil
```

## How to use

```swift
myVar = "This is my var"

// force un-wrapping
print(safeVar!)

// optional binding
if let safeVar == myVar {
    print(safeVar)
}

// guard
guard let safeVar == myVar else { return }
print(safeVar)
```
