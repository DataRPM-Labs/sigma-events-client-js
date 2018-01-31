# sigma-events-client-js
Javascript client for sigma-events, provides feature to listen for Events generated

### Install
```
bower install event-engine --save-dev
```

### Usage
```javascript
var eventEngine = EventEngine.get({url : "<event engine service url>"})
```
#### `url`
Event engine service websocket url <br />
example ```ws://locahost:8082/event-stream```

### Methods
#### `addListener(query, callback)`
- Registers a listener for event matching query. 
- Returns registration identifier as string
- `query` 
  ```
  {
    code: "<event-code>", // This field should be used to filter event by code
    headers: { // This field should be used to filter event by header key/value 
      "key-to-match" : "value-to-match" // Key-Value pair
    }
  }
  ```
- `callback`
  ```
  function(event) {
    // do something
  }
  ```
  
#### `removeListener(registryId)`
- Unregisters a listener
- `registryId` : listener registration identifier
