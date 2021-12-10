# Tips and Tricks for Erlang.mk

## Common Tests

### Run CT tests in Verbose mode

If you want to see CT output in the console: 

```shell
make ct CT_OPTS="-verbosity=10"
```

### List of Available CT_OPTS

https://docs.oracle.com/cd/E36784_01/html/E36870/ct-run-1.html

## Erlang.mk 

### Erlang - Running Erlang.mk in verbose debug output mode

Sometimes it is necessary to debug how Erlang MK does what it does. 

```shell
make ct V=2
```
