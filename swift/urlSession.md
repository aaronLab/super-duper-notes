# URLSession

About URLSession

## The order for URLSession

```swift
// 1. Create URL
let url = URL(string: urlString)

if let safeURL = url {
    // 2. Create URL Session
    let session = URLSession(configuration: .default)

    // 3. Give the session a dataTask
    let task = session.dataTask(with: safeURL) { (data, response, error) in
        if error != nil {
            /// error handling
            return
        }
        /// Do Something with Data or Response
    }

    // 4. Start the task
    task.resume()
}
```
