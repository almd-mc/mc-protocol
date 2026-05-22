# mc-protocol

Minecraft protocol implementation in Almide. Handles TCP connection, packet framing, encryption (AES-128-CFB8), and compression (zlib).

## Features

- TCP connection with encryption and compression
- VarInt encoding/decoding
- Packet building and parsing
- AES-128-CFB8 via [almide/aes](https://github.com/almide/aes) (hardware-accelerated)
- Zlib compression via stdlib

## Usage

```almide
import mc_protocol

let conn = mc_protocol.connection.connect("localhost", 25565)!
let conn = mc_protocol.connection.send(conn, 0x00, handshake_data)!
let result = mc_protocol.connection.recv(conn)!
```

## Modules

- `connection` — TCP connection with encryption/compression state
- `packet` — Packet framing (build, parse, compress)
- `varint` — Minecraft VarInt/VarLong encoding
- `types` — Common protocol types
