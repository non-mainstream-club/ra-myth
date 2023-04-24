How to reproduce:

1. Replace the `"sysroot_src": "/home/foo/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/src/rust/library",` line of JSON file with your user name (or your sysroot source path).
2. Open folder `cargo-based` and `standalone` in VS Code respectively.

The [inlay hints](https://rust-analyzer.github.io/manual.html#inlay-hints) are different:

```rust
fn main() {
    let xs: [i32; 5] = [1, 2, 3, 4, 5];
    let ys: [i32; 5] = [99; 5];
}
```

```rust
fn main() {
    let xs: [i32; 5] = [1, 2, 3, 4, 5];
    let ys: [i32; _] = [99; 5];
}
```

Tested on:

```shell
$ rust-analyzer --version
rust-analyzer 0.3.1489-standalone
```
