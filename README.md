just a modified version of [luamin](https://github.com/mathiasbynens/luamin) for my [GoofyLuaUglifier](https://github.com/mopsfl/GoofyLuaUglifier) project

# Fixes:

### INCORRECT handling of () parens [#88](https://github.com/mathiasbynens/luamin/issues/88)
#### before
`(print or io.write)('done')` -> `print or io.write('done')`

`hello = (function() return "hello" end)()` -> `hello = function() return "hello" end()`

#### after:
`(print or io.write)('done')` -> `(print or io.write)('done')`

`hello=(function() return "hello" end)()` -> `a=(function()return"hello"end)()`

<br>

### vararg table indexing or something like this
#### before
`({...})[i]` -> `{...}[i]`

#### after:
`({...})[i]` -> `({...})[i]`

<br><br><br>

##### all changes are not 100% bug free
