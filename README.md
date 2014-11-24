`debug` - a port of Node.js's [debug](https://www.npmjs.org/package/debug) for
bash.

#### install

download `debug` into your project (if as a git submodule, run: `git submodule
add https://github.com/minond/debug.git vendor/minond/debug`) and source it in
any script, like so: `source ~+/vendor/minond/debug/debug`

#### usage

after installation, you can call the `debug` command, passing a label as the
first argument and a debug message as the second:

```bash
source ~+/vendor/minond/debug/debug

debug server "starting server on $HOST, port $PORT"
debug auth "authenticating $username"
```

the `DEBUG` environment variable is then used to enable these based on the
expression saved in the variable. for example, `DEBUG=* your_script` will
output *everything*, `DEBUG=route* your_script` will output anything that
starts with "route", and finally, `DEBUG=route your_script`, which will output
only calls with a name of "route".

#### colors

you can disable colors by setting a `DEBUG_COLORS` environment variable.to `0`:
`DEBUG_COLORS=0 DEBUG=* your_script`
