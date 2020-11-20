Install `circom` v0.5.30, `circomlib` v0.2.4, and `snarkjs` 0.3.44:

```
npm i
```

Install `zkutil` v0.3.2:


```
cargo install zkutil --version 0.3.2
```

Compile the `sha256_test512.circom` test circuit:

```
npx circom node_modules/circomlib/test/circuits/sha256_test512.circom -r circuit.r1cs
```

Run zkutil's trusted setup:

```
zkutil setup -c ./circuit.r1cs
```

Error output:

```
Loading circuit from ./circuit.r1cs...
Generating trusted setup parameters...
thread 'main' panicked at 'called `Result::unwrap()` on an `Err` value: UnconstrainedVariable', /home/di/.cargo/registry/src/github.com-1ecc6299db9ec823/zkutil-0.3.2/src/main.rs:204:18
note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
```

The same error occurs even when `circom` is invoked with the `-f` flag to build the R1CS file.
