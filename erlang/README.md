# Tips and Tricks for Erlang

## Common Test

### Run CT tests in Verbose mode

If you want to see CT output in the console: 

```shell
make ct CT_OPTS="-verbosity=10"
```

### List of Available CT_OPTS

https://docs.oracle.com/cd/E36784_01/html/E36870/ct-run-1.html

## Erlang.mk 

### Running Erlang.mk in verbose debug output mode

Sometimes it is necessary to debug how Erlang MK does what it does. 

```shell
make ct V=2
```

## Lists

### lists:flatten

`lists:flatten` does not flatten a single level of a list, it flattens a "deep" list, meaning that it flattens as long as it finds a list. 

For example: 

```erlang
lists:flatten([a, [b, [c]]]).
[a,b,c]
```

Instead, something like this can be used: 

```erlang
flat_one(List) -> lists:flatmap( fun(L) -> L end, List).

flat_one([a, [b, [c]]]).
[a, b, [c]]

```

This is important because many times in Erlang you use `proplists` which are lists, and if you flatten a list of proplists, then you will run into issues. 
This is also the reason why on an `iolist` you can call `lists:flatten` to flatten it. 


