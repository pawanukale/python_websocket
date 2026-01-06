# Python WebSocket Project

A simple WebSocket server-client implementation using Python's `websockets` library and `asyncio`.

## Overview

This project demonstrates real-time bidirectional communication between a WebSocket server and client. The server echoes back messages prefixed with "Pong:" to any connected client.

## Features

- Asynchronous WebSocket server implementation
- Simple echo functionality with "Pong:" prefix
- Connection and disconnection handling
- Real-time message exchange

## Requirements

- Python 3.7 or higher
- websockets library

## Installation

1. Clone or download this repository

2. Install the required dependency:
```bash
pip install websockets
```

## Project Structure

```
python_websocket/
├── server.py    # WebSocket server implementation
├── client.py    # WebSocket client implementation
└── README.md    # This file
```

## Usage

### Running the Server

Start the WebSocket server first:

```bash
python server.py
```

The server will start listening on `localhost:7890` and display:
```
Server listening on Port 7890
```

### Running the Client

In a separate terminal, run the client:

```bash
python client.py
```

The client will:
1. Connect to the server at `ws://127.0.0.1:7890`
2. Send "Hello Server!" message
3. Listen for and print incoming messages from the server

## How It Works

### Server (`server.py`)

- Listens on port **7890**
- Accepts WebSocket connections
- Logs client connections and disconnections
- Echoes back received messages with "Pong:" prefix
- Uses `asyncio` event loop for asynchronous operations

### Client (`client.py`)

- Connects to the server at `ws://127.0.0.1:7890`
- Sends an initial "Hello Server!" message
- Continuously listens for messages from the server
- Prints received messages to the console

## Example Output

**Server Terminal:**
```
Server listening on Port 7890
A client just connected
Received message from client: Hello Server!
```

**Client Terminal:**
```
Pong: Hello Server!
```

## Configuration

To change the server port, modify the `PORT` variable in both files:

**server.py:**
```python
PORT = 7890  # Change to your desired port
```

**client.py:**
```python
url = "ws://127.0.0.1:7890"  # Update port number
```

## Error Handling

- The server gracefully handles client disconnections using `ConnectionClosed` exception
- Connection errors are caught and logged appropriately

## Stopping the Application

- Press `Ctrl+C` in the terminal to stop the server or client

## License

This project is provided as-is for educational purposes.

## Contributing

Feel free to fork this project and submit pull requests for any improvements.
