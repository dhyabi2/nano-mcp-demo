# NANO MCP Server Demo

This is a demonstration of a NANO MCP (Merchant Crypto Payment) server implementation that provides cryptocurrency payment processing capabilities.

## Features

- Initialize server with custom configuration
- Handle various cryptocurrency operations
- Support for multiple payment methods
- Real-time transaction processing
- Secure RPC communication

## Prerequisites

- Node.js v16.0.0 or higher
- npm (Node Package Manager)

## Installation

1. Clone this repository or create a new directory:
```bash
mkdir nano-mcp-demo
cd nano-mcp-demo
```

2. Initialize a new Node.js project:
```bash
npm init -y
```

3. Install the required dependencies:
```bash
npm install nano-mcp
```

## Configuration

The server uses the following configuration parameters:

```javascript
{
    publicKey: 'PUBLIC-KEY-FA9CE81226BF478291D34836A09D8B06',
    rpcKey: 'RPC-KEY-BAB822FCCDAE42ECB7A331CCAAAA23',
    port: 8000,
    host: '127.0.0.1'
}
```

- `publicKey`: Your NANO MCP public key for authentication
- `rpcKey`: Your NANO MCP RPC key for secure communication
- `port`: The port number the server will listen on (default: 8000)
- `host`: The host address to bind to (default: 127.0.0.1)

## Project Structure

```
nano-mcp-demo/
├── package.json
├── server.js
└── README.md
```

## Available Methods

The server supports the following methods:

- `initialize`: Initialize the server and get version information
- `getBalance`: Get account balance
- `getAccountInfo`: Retrieve account information
- `getBlockCount`: Get the current block count
- `getVersion`: Get server version
- `convertToNano`: Convert from raw to NANO
- `convertFromNano`: Convert from NANO to raw

## Running the Server

1. Start the server:
```bash
node server.js
```

2. The server will output initialization information and start listening for requests:
```
Starting NANO MCP Server...
MCPServer initialized with config: { name: 'NANO', version: '1.0.0' }
Registering handler for method: initialize
Registering handler for method: generateWallet
Registering handler for method: getBalance
Registering handler for method: initializeAccount
Registering handler for method: sendTransaction
Registering handler for method: receivePending
Server started successfully!
```

## Error Handling

The server implements robust error handling:
- Connection errors are logged with detailed information
- Invalid requests return appropriate error messages
- Transaction failures are properly handled and reported

## Security

- All RPC communications are authenticated using the provided keys
- Requests are validated before processing
- Sensitive operations require proper authorization

## Shutdown

The server can be gracefully shut down using `Ctrl+C` (SIGINT signal). This ensures:
- All pending operations are completed
- Connections are properly closed
- Resources are released

## Development

This demo is built using ES modules. Make sure your `package.json` includes:
```json
{
  "type": "module"
}
```

## License

ISC

## Support

For issues and feature requests, please open an issue in the repository.

## Disclaimer

This is a demonstration server and should be properly secured before use in a production environment. Always follow security best practices when handling cryptocurrency transactions. 