# Testing Number Window API with Thunder Client

## Overview
This document provides instructions for testing the Number Window API implementation using Thunder Client. The API handles different types of numbers and maintains a sliding window of values.

## Base URL
```
http://localhost:9876/numbers
```

## Endpoints

### 1. Add Even Numbers
- **Endpoint**: `/even`
- **Method**: GET
- **Description**: Returns even numbers within the sliding window
- **Example Response**:
```json
{
  "windowPrevState": [2, 4, 6],
  "windowCurrState": [2, 4, 6, 8],
  "numbers": [2, 4, 6, 8],
  "avg": 5
}
```

### 2. Add Prime Numbers
- **Endpoint**: `/prime`
- **Method**: GET
- **Description**: Returns prime numbers within the sliding window
- **Example Response**:
```json
{
  "windowPrevState": [2, 3, 5],
  "windowCurrState": [2, 3, 5, 7],
  "numbers": [2, 3, 5, 7],
  "avg": 4.25
}
```

### 3. Add Fibonacci Numbers
- **Endpoint**: `/fibonacci`
- **Method**: GET
- **Description**: Returns Fibonacci numbers within the sliding window
- **Example Response**:
```json
{
  "windowPrevState": [1, 1, 2],
  "windowCurrState": [1, 2, 3],
  "numbers": [1, 2, 3],
  "avg": 2
}
```

### 4. Add Random Numbers
- **Endpoint**: `/random`
- **Method**: GET
- **Description**: Returns random numbers within the sliding window
- **Example Response**:
```json
{
  "windowPrevState": [15, 23, 8],
  "windowCurrState": [23, 8, 42],
  "numbers": [15, 23, 8, 42],
  "avg": 24.33
}
```

## Testing Steps

1. **Create a New Request**
   - Open Thunder Client in VS Code
   - Click "New Request" button
   - Set the request method to GET

2. **Configure Request URL**
   - Enter the base URL with desired endpoint
   - Example: `http://localhost:9876/numbers/even`

3. **Send Request**
   - Click "Send" button to make the request
   - Verify the response contains:
     - `windowPrevState`: Previous state of the sliding window
     - `windowCurrState`: Current state after adding new number
     - `numbers`: All unique numbers seen so far
     - `avg`: Average of current window numbers

4. **Verify Sliding Window Behavior**
   - Make multiple requests to the same endpoint
   - Confirm the window shifts correctly when size limit is reached
   - Check that numbers array contains all unique values
   - Verify average calculation is correct

## Response Validation

- Ensure response is valid JSON
- Check that all required fields are present
- Verify number values are integers
- Confirm average is rounded to 2 decimal places
- Validate that windowCurrState length doesn't exceed window size

## Error Cases

- Invalid endpoint returns 404
- Server errors return 500 series status codes
- Non-integer values are ignored by the NumberWindow class