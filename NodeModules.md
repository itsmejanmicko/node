# Node.js Modules Reference

This document provides a quick reference to commonly used Node.js modules, their descriptions, and key methods or properties, along with example usage.

| **Module**         | **Description**                          | **Common Methods / Properties**                                                                 |
|---------------------|------------------------------------------|-------------------------------------------------------------------------------------------------|
| `fs`               | File system operations                  | `readFile()`, `writeFile()`, `readdir()`, `mkdir()`, `stat()`, `unlink()`                       |

### Examples

#### `fs` Module
```javascript
const fs = require('fs');

// readFile
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});

// writeFile
fs.writeFile('example.txt', 'Hello, World!', (err) => {
  if (err) throw err;
  console.log('File written successfully');
});

// mkdir
fs.mkdir('newFolder', (err) => {
  if (err) throw err;
  console.log('Directory created');
});
```

| `path`             | Utilities for file and directory paths  | `join()`, `resolve()`, `basename()`, `dirname()`, `extname()`, `parse()`, `format()`           |

#### `path` Module
```javascript
const path = require('path');

// join
const fullPath = path.join('/folder', 'subfolder', 'file.txt');
console.log(fullPath);

// resolve
const resolvedPath = path.resolve('file.txt');
console.log(resolvedPath);

// basename
const base = path.basename('/folder/file.txt');
console.log(base);
```

| `http`             | Build HTTP server and client            | `createServer()`, `request()`, `get()`                                                        |

#### `http` Module
```javascript
const http = require('http');

// createServer
const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello, World!\n');
});
server.listen(3000, () => console.log('Server running on port 3000'));

// request
const options = { hostname: 'example.com', port: 80, path: '/', method: 'GET' };
const req = http.request(options, (res) => {
  res.on('data', (chunk) => console.log(chunk.toString()));
});
req.end();
```

| `https`            | HTTP over SSL/TLS                       | `createServer()`, `request()`, `get()`                                                        |

#### `https` Module
```javascript
const https = require('https');

// createServer
const httpsServer = https.createServer({}, (req, res) => {
  res.writeHead(200);
  res.end('Secure Server');
});
httpsServer.listen(8443);

// get
https.get('https://example.com', (res) => {
  res.on('data', (chunk) => console.log(chunk.toString()));
});
```

| `os`               | System and OS-level information         | `cpus()`, `freemem()`, `totalmem()`, `hostname()`, `platform()`, `uptime()`                   |

#### `os` Module
```javascript
const os = require('os');

console.log('CPUs:', os.cpus());
console.log('Free memory:', os.freemem());
console.log('Total memory:', os.totalmem());
console.log('Hostname:', os.hostname());
console.log('Platform:', os.platform());
console.log('Uptime:', os.uptime());
```

| `events`           | Event-driven programming support        | `EventEmitter`, `on()`, `emit()`, `removeListener()`, `once()`                                |

#### `events` Module
```javascript
const EventEmitter = require('events');

const emitter = new EventEmitter();

emitter.on('event', () => console.log('An event occurred!'));
emitter.emit('event');
```

| `util`             | Utilities for debugging and transformations | `format()`, `promisify()`, `inherits()`, `inspect()`                                         |

#### `util` Module
```javascript
const util = require('util');

// format
console.log(util.format('%s:%d', 'Hello', 123));

// promisify
const readFile = util.promisify(fs.readFile);
readFile('example.txt', 'utf8').then(console.log);
```

| `buffer`           | Handling binary data                    | `Buffer.from()`, `Buffer.alloc()`, `toString()`, `toJSON()`, `byteLength()`                   |

#### `buffer` Module
```javascript
const buffer = Buffer.from('Hello');
console.log(buffer.toString());
console.log(buffer.byteLength);
```

| `crypto`           | Cryptographic functionality             | `createHash()`, `createCipher()`, `createDecipher()`, `randomBytes()`, `pbkdf2()`             |

#### `crypto` Module
```javascript
const crypto = require('crypto');

const hash = crypto.createHash('sha256').update('data').digest('hex');
console.log(hash);

crypto.randomBytes(16, (err, buf) => {
  if (err) throw err;
  console.log('Random bytes:', buf.toString('hex'));
});
```

| `stream`           | Handling streams of data                | `Readable`, `Writable`, `Transform`, `Duplex`                                                |

#### `stream` Module
```javascript
const { Readable } = require('stream');

const readable = Readable.from(['data1', 'data2']);
readable.on('data', (chunk) => console.log(chunk.toString()));
```

| `querystring`      | Parsing and formatting URL query strings | `parse()`, `stringify()`                                                                      |

#### `querystring` Module
```javascript
const querystring = require('querystring');

const parsed = querystring.parse('key=value&key2=value2');
console.log(parsed);

const stringified = querystring.stringify({ key: 'value', key2: 'value2' });
console.log(stringified);
```

| `url`              | Parsing and formatting URLs             | `parse()`, `format()`, `URL` (constructor)                                                   |

#### `url` Module
```javascript
const url = require('url');

const parsedUrl = new url.URL('https://example.com/path?name=test');
console.log(parsedUrl.hostname);
console.log(parsedUrl.searchParams.get('name'));
```

| `child_process`    | Running child processes                 | `exec()`, `spawn()`, `fork()`, `execFile()`                                                  |

#### `child_process` Module
```javascript
const { exec } = require('child_process');

exec('ls', (err, stdout) => {
  if (err) throw err;
  console.log(stdout);
});
```

| `zlib`             | Compression and decompression           | `gzip()`, `gunzip()`, `deflate()`, `inflate()`, `createGzip()`, `createGunzip()`              |

#### `zlib` Module
```javascript
const zlib = require('zlib');

const input = 'Hello';
zlib.gzip(input, (err, buffer) => {
  if (err) throw err;
  console.log('Compressed:', buffer.toString('hex'));
});
```

| `dns`              | DNS resolution                          | `lookup()`, `resolve()`, `reverse()`, `getServers()`                                          |

#### `dns` Module
```javascript
const dns = require('dns');

dns.lookup('example.com', (err, address) => {
  if (err) throw err;
  console.log('Address:', address);
});
```

| `timers`           | Scheduling timers                       | `setTimeout()`, `setInterval()`, `setImmediate()`, `clearTimeout()`                           |

#### `timers` Module
```javascript
// setTimeout
setTimeout(() => console.log('Timeout executed'), 1000);

// setInterval
const interval = setInterval(() => console.log('Interval running'), 1000);

// Clear the interval after 5 seconds
setTimeout(() => clearInterval(interval), 5000);
```
