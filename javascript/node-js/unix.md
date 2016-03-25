# Unix

## How to run bash commands from NodeJS

> use [`child_process.exec`](https://nodejs.org/api/child_process.html#child_process_child_process_exec_command_options_callback) to run bash commands

```javascript
var exec = require('child_process').exec;
var child;
// executes `pwd`
child = exec("pwd", function (error, stdout, stderr) {
  sys.print('stdout: ' + stdout);
  sys.print('stderr: ' + stderr);
  if (error !== null) {
    console.log('exec error: ' + error);
  }
});
```

