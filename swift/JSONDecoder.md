# JSONDecoder

About JSONDecoder

## The order for URLSession

> Declare Decoder -> Create a Struct to decode the data -> Decode Data with the Struct

## Example

1. WeatherData.swift

   ```swift
   struct WeatherData: Decodable {
       let name: String
       let main: Main
       let weather: [Weather]
   }

   struct Main: Decodable {
       let temp: Double
   }

   struct Weather: Decodable {
       let description: String
   }
   ```

2. WeatherManager.swift

   ```swift
    struct WeatherManager {
       func parseJSON(weatherData: Data) {
            let decoder = JSONDecoder()
            do {
                let decodedData = try decoder.decode(WeatherData.self, from: weatherData)
                // Do Something with decodedData
                print("Name: \(decodedData.name), Temp: \(decodedData.main.temp), Description: \(decodedData.weather[0].description)")
            } catch {
                // Error Handle
                print(error)
            }
        }
    }
   ```
