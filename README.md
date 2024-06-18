just a modified version of [luamin](https://github.com/mathiasbynens/luamin/issues/88) for my [GoofyLuaUglifier](https://github.com/mopsfl/GoofyLuaUglifier) project

# Fixes:

### INCORRECT handling of () parens [#88](https://github.com/mathiasbynens/luamin/issues/88)
#### before
`(print or io.write)('done')` -> `print or io.write('done')`

`hello = (function() return "hello" end)()` -> `hello = function() return "hello" end()`

#### after:
`(print or io.write)('done')` -> `(print or io.write)('done')`

`hello=(function() return "hello" end)()` -> `a=(function()return"hello"end)()`

<br><br><br>

> ##### All changes and fixes are not 100% tested and might break something
