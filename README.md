just a modified version of [luamin](https://github.com/mathiasbynens/luamin/issues/88)

# things i fixed:

### INCORRECT handling of () parens [#88](https://github.com/mathiasbynens/luamin/issues/88)
#### before
> (print or io.write)('done') -> print or io.write('done')
>  hello = (function() return "hello" end)() -> hello = function() return "hello" end()

#### after:
> print or io.write('done') -> (print or io.write)('done')
> a=(function()return"hello"end)()

<br><br><br>

##### all changes are not 100% bug free