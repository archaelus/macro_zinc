# The #[zinc_main] Macro

This library provides a macro allowing you to easily set your main function to be a reset vector for startup in embedded firmware.

This code is derived from [Zinc.rs](https://github.com/hackndev/zinc) - many thanks to them.


### Updating from upstream Zinc

`git subtree split --prefix=macro_zinc -b mz_split` in the Zinc repo. Then pull the `mz_split` branch into this repo as `mz_split`. Then rebase `master` onto `mz_split`.

## Building

If you want to build this library as a standalone rlib:
```
$ xargo build
```

## Setup

Generally you'll include this in your own project 
```toml
[dependencies.macro_zinc]
git = "https://github.com/archaelus/macro_zinc"
```

You can use the macro by including it as a compiler plugin:
```rust
#![feature(plugin, start)]
#![no_std]
#![plugin(macro_zinc)]

#[zinc_main]
pub fn main() {
...
}
```
