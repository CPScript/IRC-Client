# IRC - Internet Relay Client

A command-line IRC client written in C that allows users to connect to IRC servers, join channels, and send messages. This program provides a simple and reliable interface for interacting with IRC networks.

<img width="679" height="217" alt="image" src="https://github.com/user-attachments/assets/4b737ce1-59bb-49f7-93d9-2363be5e9e46" />

TODO | Is Done?
---|---
Make a graphical version | [Check out; Nexus](https://github.com/IRC-Graphical/Nexus)


## Features

- Robust hostname resolution supporting both domain names and IP addresses
- Concurrent input/output handling using POSIX threads
- Full IRC protocol compliance with proper handshake implementation
- PING/PONG keepalive handling for stable connections
- Signal handling for clean shutdown procedures
- Comprehensive error handling and logging system
- Memory-safe string operations and buffer management
- Modular code architecture for maintainability

## Building

Navigate to the project directory and compile using make:

```
make
```

The executable will be created as `bin/ircy`.

For debug builds with additional logging:

```
make debug
```

## Usage

Run the client with required parameters:

```
./bin/ircy -s <server> -n <nickname> -c <channel>
```

### Parameters

- `-s <server>`: IRC server hostname or IP address
- `-n <nickname>`: Your desired nickname on the network
- `-c <channel>`: Channel to join upon connection

### Example

```
./bin/ircy -s irc.libera.chat -n myuser -c general
```

## Commands

Once connected, you can use standard IRC commands:

- Type messages normally to send to the current channel
- `/join #channelname` - Join a different channel
- `/quit` - Exit the client cleanly

## Network Requirements

- Standard IRC port 6667 is used for all connections
- IPv4 support required (IPv6 planned for future releases)
- Outbound TCP connections must be permitted through firewalls

## Implementation Details

The client uses a multi-threaded architecture:

- Main thread handles initialization and coordination
- Input thread processes user commands and keyboard input
- Server thread manages incoming IRC messages and protocol responses

All network operations use standard POSIX socket APIs with proper error handling. The code follows C99 standards with POSIX extensions for threading and network functions.

## Installation

To install system-wide:

```
make install
```

This copies the binary to `/usr/local/bin/ircy`.

## Compatibility

Tested on Linux systems with gcc compiler. Requires:

- POSIX-compliant system
- pthread library support
- Standard C library with networking functions

## License

This project is licensed under the MIT License.
