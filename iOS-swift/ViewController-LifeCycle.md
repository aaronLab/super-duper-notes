# Life Cycle

About Life Cycle

## Cycle

1. viewDidLoad()
2. viewWillAppear()
3. **The view appeared.**
4. viewDidAppear()
5. **Right before leaving the view.**
6. viewWillDisappear()
7. **The view disappeared.**
8. viewDidDisappear()

## Example

> When move from ViewController1 to ViewController2, and then go back to ViewController1

```swift
// ViewController1.swift

class ViewController1: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        print("1-1. viewDidLoad Called")
    }

    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)
        print("1-2. viewWillAppear Called")
    }

    // 1-3. The view appeared.

    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        print("1-4. viewDidAppear Called")
    }

    // 1-5. Right before leaving the view.

    override func viewWillDisappear(_ animated: Bool) {
        super.viewWillDisappear(animated)
        print("1-6. viewWillDisappear Called")
    }

    // 1-7. The view disappeared.

    override func viewDidDisappear(_ animated: Bool) {
        super.viewDidDisappear(animated)
        print("1-8. viewDidDisappear Called")
    }

}
```

```swift
// ViewController2.swift

class ViewController2: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        print("2-1. viewDidLoad Called")
    }

    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)
        print("2-2. viewWillAppear Called")
    }

    // 2-3. The view appeared.

    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        print("2-4. viewDidAppear Called")
    }

    // 2-5. Right before leaving the view.

    override func viewWillDisappear(_ animated: Bool) {
        super.viewWillDisappear(animated)
        print("2-6. viewWillDisappear Called")
    }

    // 2-7. The view disappeared.

    override func viewDidDisappear(_ animated: Bool) {
        super.viewDidDisappear(animated)
        print("2-8. viewDidDisappear Called")
    }

}
```

> Result

- **_Modally_**

  ```swift
  // As soon as Run
  print("1-1. viewDidLoad Called")
  print("1-2. viewWillAppear Called")
  print("1-4. viewDidAppear Called")
  // Show VC2 Modally
  print("2-1. viewDidLoad Called")
  print("2-2. viewWillAppear Called")
  print("2-4. viewDidAppear Called")
  // Dismiss VC2
  print("2-6. viewWillDisappear Called")
  print("2-8. viewDidDisappear Called")
  ```

- **_Full Screen_**

  ```swift
  // As soon as Run
  print("1-1. viewDidLoad Called")
  print("1-2. viewWillAppear Called")
  print("1-4. viewDidAppear Called")
  // Show VC2
  print("2-1. viewDidLoad Called")
  print("1-6. viewWillDisappear Called")  // Important!
  print("2-2. viewWillAppear Called")
  print("2-4. viewDidAppear Called")
  print("1-8. viewDidDisappear Called")  // Important!
  // Dismiss VC2
  print("2-6. viewWillDisappear Called")
  print("1-2. viewWillAppear Called")
  print("1-4. viewDidAppear Called")
  print("2-8. viewDidDisappear Called")  // Important!
  ```
