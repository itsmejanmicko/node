# Node.js Modules Reference

This document provides a quick reference to commonly used Node.js modules, their descriptions, and key methods or properties.

| **Module**         | **Description**                          | **Common Methods / Properties**                                                                 |
|---------------------|------------------------------------------|-------------------------------------------------------------------------------------------------|
| `fs`               | File system operations                  | `readFile()`, `writeFile()`, `readdir()`, `mkdir()`, `stat()`, `unlink()`                       |
| `path`             | Utilities for file and directory paths  | `join()`, `resolve()`, `basename()`, `dirname()`, `extname()`, `parse()`, `format()`           |
| `http`             | Build HTTP server and client            | `createServer()`, `request()`, `get()`                                                        |
| `https`            | HTTP over SSL/TLS                       | `createServer()`, `request()`, `get()`                                                        |
| `os`               | System and OS-level information         | `cpus()`, `freemem()`, `totalmem()`, `hostname()`, `platform()`, `uptime()`                   |
| `events`           | Event-driven programming support        | `EventEmitter`, `on()`, `emit()`, `removeListener()`, `once()`                                |
| `util`             | Utilities for debugging and transformations | `format()`, `promisify()`, `inherits()`, `inspect()`                                         |
| `buffer`           | Handling binary data                    | `Buffer.from()`, `Buffer.alloc()`, `toString()`, `toJSON()`, `byteLength()`                   |
| `crypto`           | Cryptographic functionality             | `createHash()`, `createCipher()`, `createDecipher()`, `randomBytes()`, `pbkdf2()`             |
| `stream`           | Handling streams of data                | `Readable`, `Writable`, `Transform`, `Duplex`                                                |
| `querystring`      | Parsing and formatting URL query strings | `parse()`, `stringify()`                                                                      |
| `url`              | Parsing and formatting URLs             | `parse()`, `format()`, `URL` (constructor)                                                   |
| `child_process`    | Running child processes                 | `exec()`, `spawn()`, `fork()`, `execFile()`                                                  |
| `zlib`             | Compression and decompression           | `gzip()`, `gunzip()`, `deflate()`, `inflate()`, `createGzip()`, `createGunzip()`              |
| `dns`              | DNS resolution                          | `lookup()`, `resolve()`, `reverse()`, `getServers()`                                          |
| `timers`           | Scheduling timers                       | `setTimeout()`, `setInterval()`, `setImmediate()`, `clearTimeout()`                           |

## Usage
Refer to this table to quickly find methods and utilities provided by core Node.js modules for various operations like file handling, networking, and more.
