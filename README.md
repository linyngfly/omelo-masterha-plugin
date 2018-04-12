omelo-masterha-plugin
======================

master ha plugin for omelo, it can be used in omelo(>=0.6).

omelo-masterha-plugin is a master ha plugin for omelo, which uses zookeeper to make master as high availability cluster.

##Installation

```
npm install omelo-masterha-plugin
```

##Usage

Make sure you have installed zookeeper first, then you have built the path you pass to omelo. The configure code in app.js is as follows:

```
var masterhaPlugin = require('omelo-masterha-plugin');

app.configure('production|development', function() {
  
  app.use(masterhaPlugin, {
    zookeeper: {
      server: '127.0.0.1:2181',
      path: '/omelo/master'
    }
  });

});

```

You can start your application using omelo start as before, then use [omelo-daemon](https://github.com/fantasyni/omelo-daemon) to start a slave master.
