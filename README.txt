# Temperature Cache in Rust

This Rust application provides a performant and robust cache for fetching and updating the current temperature of tracked cities through a provided API. The cache aims to minimize the need for asynchronous network calls by keeping a map of cities and their temperatures up to date in the background.

## Features

- **Efficient Caching:** The cache stores the most recent temperature values for tracked cities, reducing the need for slow and expensive fetch calls.
- **Background Updates:** Utilizes a background thread to subscribe to incremental updates, ensuring that the cache always reflects the latest temperature information.
- **Simple API Interface:** The API allows consumers to easily retrieve the current temperature for any tracked city without asynchronous network calls.

## Getting Started

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd temperature-cache-rust





1) Run Tests:
cargo test

2) Explore the Implementation:

main.rs: Contains the main implementation of the temperature cache and API.
tests.rs: Includes a basic test to verify the functionality of the cache.

3) Integrate with Your API:

Replace the simulated TemperatureApi with the actual API structure and implementation.
Adjust the API calls, error handling, and edge cases based on your specific requirements. 




USAGE:-
use temperature_cache::TemperatureCache;

fn main() {
    // Create a new instance of the TemperatureCache
    let api = temperature_cache::TemperatureApi::new();
    let cache = temperature_cache::TemperatureCache::new(api);

    // Retrieve the current temperature for a city
    let temperature = cache.get_temperature("City1");
    println!("Temperature for City1: {}°C", temperature);

    // Subscribe to updates and handle changes
    cache.subscribe_to_updates(Box::new(|temperatures| {
        // Handle updated temperatures
        println!("Received updated temperatures: {:?}", temperatures);
    }));
}



Contribution
Feel free to contribute to this project by submitting issues, feature requests, or pull requests.


