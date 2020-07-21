# geckodriver
geckodriver source code from mozilla official website

# mozilla-central
https://hg.mozilla.org/mozilla-central/file/tip/testing

# build
1.install rust

2.rustup toolchain install stable-i686-pc-windows-msvc

3.rustup toolchain install stable-i686-pc-windows-msvc

4.configure file [~/.cargo/config]
```
[source.crates-io]
replace-with = 'ustc'
[source.ustc]
registry = "https://mirrors.ustc.edu.cn/crates.io-index"
[http]
check-revoke = false
[target.x86_64-pc-windows-msvc]
rustflags = ["-C", "target-feature=+crt-static"]

[target.i686-pc-windows-msvc]
rustflags = ["-C", "target-feature=+crt-static"]
```
5.build
```
cd mozilla-central\testing\geckodriver
rustup default stable-x86_64-pc-windows-msvc
cargo build --release
rustup default stable-i686-pc-windows-msvc
cargo build --release
```
