---
tableOfContents: true
---

# Configuration

## Introduction
There are only a few settings to pass for now. Most things are controlled through [hooks](/api/hooks).

## Settings

### name
A name for the instance, used for logging.

### port
The port the server should listen on.

Default: `80`

### timeout
A connection healthcheck interval in milliseconds.

Default: `30000` (= 30s)

### debounce
Debounces the call of the `onStoreDocument` hook for the given amount of time in ms. Otherwise every single update would be persisted.

Default: `2000` (= 2s)

### maxDebounce
Makes sure to call `onStoreDocument` at least in the given amount of time (ms).

Default: `10000` (= 10s)

### quiet
By default, the servers show a start screen. If passed false, the server will start quietly.

Default: `false`

## Usage
```js
import { Server } from '@hocuspocus/server'

const server = Server.configure({
  name: 'hocuspocus-fra1-01',
  port: 1234,
  timeout: 30000,
  debounce: 5000,
  maxDebounce: 30000,
  quiet: true,
})

server.listen()
```
