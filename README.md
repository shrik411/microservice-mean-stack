# microservice-mean-stack
Brief methods and concepts used for basic microservice development with MEAN stack

Node.js

install express library

```
var express = require('express');
var app = express();

app.get('/', function(req, res) {
  res.send('Hello World!');
});

app.listen(3000, function() {
  console.log('Example app listening on port 3000!');
});
```

body-parse 

```
var express = require('express')
var bodyParser = require('body-parser')

var app = express()

// parse application/x-www-form-urlencoded
app.use(bodyParser.urlencoded({ extended: false }))

// parse application/json
app.use(bodyParser.json())

app.use(function (req, res) {
  res.setHeader('Content-Type', 'text/plain')
  res.write('you posted:\n')
  res.end(JSON.stringify(req.body, null, 2))
})
```

mongoos example

Connecting
```
//Import the mongoose module
var mongoose = require('mongoose');

//Set up default mongoose connection
var mongoDB = 'mongodb://127.0.0.1/my_database';
mongoose.connect(mongoDB, { useNewUrlParser: true });

//Get the default connection
var db = mongoose.connection;

//Bind connection to error event (to get notification of connection errors)
db.on('error', console.error.bind(console, 'MongoDB connection error:'));
```

Defining and creating models

Defining schemas

```
//Require Mongoose
var mongoose = require('mongoose');

//Define a schema
var kittySchema = new mongoose.Schema({
  name: String
});
```

Creating a model

```
var Kitten = mongoose.model('Kitten', kittySchema);
```

Fetch
```
var silence = new Kitten({ name: 'Silence' });
console.log(silence.name); // 'Silence'
```




