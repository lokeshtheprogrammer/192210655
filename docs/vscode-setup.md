# Running the Number Window Application in VS Code

## Prerequisites
- Visual Studio Code installed
- Node.js and npm installed
- Git (optional, for version control)

## Setup Instructions

1. Open the project in VS Code:
   - Launch VS Code
   - Go to File > Open Folder
   - Navigate to and select the project folder

2. Install Dependencies:
   ```bash
   npm install
   ```

## Running the Application

### Development Mode
To start the server in development mode:
```bash
 npm run dev
```
This will start the server with hot-reload enabled.

### Production Mode
To run the server in production mode:
```bash
node src/index.js
```

## Port Configuration
- Default port: 9876
- The server will automatically find an available port if 9876 is in use
- You can set a custom port using the PORT environment variable:
  ```bash
  PORT=3000 node src/index.js
  ```

## Verifying the Server
1. Once started, you should see a message: `Server running on port XXXX`
2. Test the API endpoints using Thunder Client or your browser:
   - Even numbers: `http://localhost:XXXX/numbers/e`
   - Prime numbers: `http://localhost:XXXX/numbers/p`
   - Fibonacci numbers: `http://localhost:XXXX/numbers/f`
   - Random numbers: `http://localhost:XXXX/numbers/r`

## Debugging in VS Code
1. Set breakpoints by clicking the left margin of the code editor
2. Press F5 or go to Run > Start Debugging
3. Select "Node.js" as the debug configuration

## Common VS Code Commands
- `Ctrl + ` `: Open/close integrated terminal
- `Ctrl + Shift + P`: Open command palette
- `F5`: Start debugging
- `Shift + F5`: Stop debugging
- `Ctrl + S`: Save file

## Troubleshooting
- If the server fails to start, check if the port is already in use
- Ensure all dependencies are installed correctly
- Check the console for error messages
- Verify the API token is valid and not expired