# cylon [![Build Status](https://secure.travis-ci.org/hybridgroup/cylon.png?branch=master)](http://travis-ci.org/hybridgroup/cylon)

Cylon.js is a JavaScript framework for robotics and physical computing using node.js

It provides a simple, yet powerful way to create solutions that incorporate multiple, different hardware devices at the same time.

## Getting Started

Install the module with: `npm install cylon`

## Examples

**Note:** before running examples in the `examples/` dir, make sure to compile
the source with `grunt coffee` first.

### Javascript:
```javascript
var Cylon = require("cylon");

// Initialize the robot
var robot = Cylon.robot({
  connection: { name: 'arduino', adaptor: 'firmata', port: '/dev/ttyACM0' },
  device: { name: 'led', driver: 'led', pin: 13 },

  work: function() {
    // we do our thing here
    every((1).second(), function() { led.toggle(); });
  }
});

// start working
robot.start();
```

### CoffeeScript:
```coffee-script
Cylon = require "cylon"

# Initialize the robot
robot = Cylon.robot
  connection:
    name: 'arduino'
    adaptor: 'firmata'
    port: '/dev/ttyACM0'

  device:
    name: 'led'
    driver: 'led'
    pin: 13

  work: ->
    # we do our thing here
    every 1.second, -> led.toggle

robot.start
```

## Documentation
_(Coming soon)_

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style.
Add unit tests for any new or changed functionality. Lint and test your code
using [Grunt](http://gruntjs.com/).

## Release History
_(Nothing yet)_

## License
Copyright (c) 2013 The Hybrid Group. Licensed under the Apache 2.0 license.