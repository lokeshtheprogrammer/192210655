# Number Window API

A RESTful API service that maintains a sliding window of numbers from various sources (even numbers, prime numbers, fibonacci numbers, and random numbers) with a configurable window size.

## Features

- Sliding window implementation for number sequences
- Multiple number types supported:
  - Even numbers (e)
  - Prime numbers (p)
  - Fibonacci numbers (f)
  - Random numbers (r)
- Window statistics including previous state, current state, and average

## Prerequisites

- Node.js (v12 or higher)
- Java 11 or higher
- Maven

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd cal
   ```

2. Install Node.js dependencies:
   ```bash
   npm install
   ```

3. Build Java components (if applicable):
   ```bash
   mvn clean install
   ```

## Configuration

Create a `.env` file in the root directory and add your configuration:

```env
PORT=9876
API_TOKEN=your_api_token_here
```

## Usage

1. Start the server:
   ```bash
   npm start
   ```

2. Access the endpoints:
   - Even numbers: `GET /numbers/e`
   - Prime numbers: `GET /numbers/p`
   - Fibonacci numbers: `GET /numbers/f`
   - Random numbers: `GET /numbers/r`

## API Response Format

```json
{
  "windowPrevState": [2, 4, 6],
  "windowCurrState": [2, 4, 6, 8],
  "numbers": [2, 4, 6, 8],
  "avg": 5
}
```

## Development

For development, you can use the provided VS Code setup and Thunder Client collection for testing the API endpoints.

## License

MIT