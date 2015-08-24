#JSON::Faster

Wrote this, originally, for Zef because the `to-json` stuff was running _long_ and after seeing the performance improvement over built-in `to-json` and similar modules, figured I'd release this whale.

##What doesn't it do

This doesn't provide a `from-json`, you can use the built-in for it as that is fast enough; my only pain was converting `to-json`.

##Options

###`Bool :pretty? = True`

Pretty output means you get spacing and line breaks in the out instead of one long string.

###`Int :level? = 0`

The initial level of indenting for the output, 0 will insert 0 spaces before out, 1 will insert `:$spacing` spaces prior to output.  This is unused if `:$pretty` is `False`.

###`Int :spacing? = 2`

Controls how many spaces per `:$level` the output receives when `:$pretty` is `True`.  This is unused if `:$pretty` is `False`.

##Benchmark vs JSON::Fast

Why `JSON::Fast`?  Because its `to-json` performance was roughly equivalent to the built-in.

```

```

##Benchmark of `pretty` output vs `!pretty`

```
Benchmark:
Timing 30 iterations of not-pretty, pretty...
not-pretty: 61.1153 wallclock secs @ 0.4909/s (n=30)
pretty: 59.5403 wallclock secs @ 0.5039/s (n=30)
O------------O--------O------------O--------O
|            | s/iter | not-pretty | pretty |
O============O========O============O========O
| not-pretty | 2.04   | --         | -3%    |
| pretty     | 1.98   | 3%         | --     |
---------------------------------------------
```

##License

Free.  All day e'ery day.
