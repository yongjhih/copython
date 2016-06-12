# copython

Coffee Python

## TODO

Before:

```py
rx.Observable.from_(seconds).flat_map(
        lambda s: executor.submit(sleep, s)
    ).subscribe(output)
```

After:

```py
rx.Observable.from_(seconds).flat_map(s -> {
  executor.submit(sleep, s)
}).subscribe(output)
```

Internal:

```py
rx.Observable.from_(seconds).flat_map(_lambda0).subscribe(output)

def _lambda0(s) {
  executor.submit(sleep, s)
}
```
