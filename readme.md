# message util

Do things with nested messages. 

## install 

    $ npm install message-util

## example

```js
var Msg = require('message-util')
var compose = ('./compose')

// your messages are just arrays
var update = Msg('update')
var helloMsg = update('hello')  // => ['update', 'hello']
var hiMsg = update('hi')  // => ['update', 'hi']

Msg.type(hiMsg)  // => 'update'
Msg.data(hiMsg)  // => 'hi'

var composed = function (data) {
    return Msg('nest', update(data))
}

var msg = composed('ok')  // => ['nest', ['update', 'ok']]
Msg.find(['nest', 'update'])  // => ['update', 'ok']
```

