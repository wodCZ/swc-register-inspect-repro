# Reproduction of incorrect --inspect behavior of IntelliJ Node.js debugger

## Steps to reproduce
- Clone this repo
- Run `npm install`

### Option A
- Run `npm start`
- (in IDE) attach debugger using the `Debug` configuration

### Option B
- (in IDE) run the `start` configuration with the debugger attached

### Current output
In both cases you'll see that the `debugger;` statement correctly pauses the execution, but the IDE doesn't show the correct line of code.

### Expected output
The IDE should show the correct line of code.

## Considerations
- Running Option A and attaching Chrome debugger or VSCode debugger, we can see a different output, but both debuggers show the correct line of code.
- .swcrc option `sourceMaps` doesn't seem to have any effect on the output (`false`, `true` nor `'inline'`)
- Different `jsc.target` options provide different outputs, but none of them show the correct line of code in IntelliJ.