## require CMDNAME $0

require is a command for finding commands.

it works just like `require` in nodejs,  
so much so that you can use npm to install bash scripts,  
and their dependencies, and if you load them with `require`  
you'll have support for version conflicts!

so you will be able to maintain really large bash scripts\* :D 

\*by spliting them into many seperate bash scripts that you can maintain seperately of course!

`CMDNAME` is the name of the command that you are wanting to load, 
`$0` needs to be passed in so that require knows where to start looking.  
if you leave it off, it will default to $PWD,  
which will work if you are using require from the command line.


use it like this:

``` bash
  sp=`require bashscripts/smartprompt $0`

  $sp hello!
```

note that this translates pretty driectly to what it would look like if it was in nodejs.

``` js
  var smartprompt = require('bashscripts')

  smartprompt ('hello!')
```