
## Directory structure

The TyPPX-based ppx extension is in `preprocessor`. It is a trivial identity
mapper.

The app that uses it is in `app`.

## Steps to reproduce

```sh
opam install typpx
```

`make up` in the `preprocessor` directory will build the ppx extension and pin
it on opam.

After that, `make` in the `app` directory will result in

```
File "example.ml", line 2, characters 15-18:
show cannot be derived for int
```
