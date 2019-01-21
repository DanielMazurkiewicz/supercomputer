# supercomputer
NodeJS library that automates mass computation tasks across multiple GPUs (also remote ones)


!!!Do not use it! This library is not ready yet!!!


# SPIRV

This library operates on SPIRV code, if you're looking for tools to create SPIRV code then checkout these libraries/repos:

 * https://github.com/DanielMazurkiewicz/vulkan-spirv-glsl
 * https://github.com/DanielMazurkiewicz/vulkan-spirv-pretty
 * https://github.com/DanielMazurkiewicz/vulkan-spirv


# Expected usage example
```javascript
const SuperComputer = require('supercomputer');

const spirvCodeBuffer = readFromFile(); // just some basic sample
const computer = new SuperComputer(spirvCodeBuffer);

computer.execute(executionDoneCallback)
  .then(()=>{
    // ready to perform next execution
  })

```


# Expected usage example with remote connections

Client:

```javascript
const SuperComputer = require('supercomputer');
const isConnected = await SuperComputer.connectTo(address, port, token, options);

```

Server:

```javascript

const SuperComputer = require('supercomputer');

const accessToken = SuperComputer.createNewToken(); // token to share with client
await SuperComputer.acceptConnections(portNumber, options);

```