# Spectre gRPC interface

Spectre gRPC module is a basic request/response wrapper for interfacing with [Spectred](https://github.com/spectre-project/spectred)

## Cloning spectre-grpc

```
git clone https://github.com/spectre-project/spectre-grpc
cd spectre-grpc
npm install
```

## Example

```js
const { Client } = require('@spectre/grpc');

const client = new Client({
    host:"127.0.0.1:18210"
});
client.connect();
client.verbose = true;

try {
    let response = await client.call('getMempoolEntriesRequest', { });
    console.log(response);
} catch(ex) {
    ...
}

client.call('getVirtualSelectedParentBlueScoreRequest', { }).then((response)=>{
    console.log(response);
}).catch((err)=>{
    console.log('error:',err);
})
```
