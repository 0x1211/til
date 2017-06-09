# About Comma First style

## Context
Taking over a Node.js project I wanted to write using ES6 syntax I met the following statements:

```
var fs = require('fs')
    , whatev = require('whatev')
    , whatevElse = require('./whatevElse');
```

Shocked by such an ugly looking to me I wondered why would a developer write statements with comma first. This is how some researches lead me to discover that this was called "Comma First" style.

## Why Comma First ?
Using Comma First style is most likely used for some objective reasons which are the ease of spotting errors and some subjective reasons which are: code has to look nice !

See the following gist for visual explanation (note that this looks like a pro-comma-first Gist :wink:): https://gist.github.com/isaacs/357981.

## Some concerns about Comma First
Discussing this practice with the superstar of this repository: Mr @taxigy, we arrived at the following conclusions on Comma First style:
* it looks ugly (subjective)
* error spotting has to be handled by the developer, and in case the developer fails: its editor. 
