# superserialize

superserialize is an advanced serialization system, which allows you to serialize
JavaScript objects, including their functions, into a JSON-compatible data structure.
the JSON can then be sent across a socket, HTTP, or whatever you wish. Once the JSON
has been sent to the destination, superserialize can then deserialize it back into
a JavaScript object, complete with working functions.

# Usage Example

```javascript
var serialize = require('superserialize').serialize,
	deseralize = require('superserialize').deserialize;
	
var TestObject = {
	sayHello: function(name) {
		console.log(name + ": Hi there!");
	}
};

var serialized = serialize(TestObject);

console.log(serialized); // This will output a JSON-compatible object

var deserialized = deserialize(serialized);

deserialize.sayHello("Bob"); // This will output "Bob: Hi there!" as expected!
```

# Installation

To use superserialize, just run ``npm install superserialize``. There are no
dependencies and you can use superserialize in the browser with the ``browserify``
module.

# License

superserialize was created by Jesse Dunlap, and is licensed under the MIT license.