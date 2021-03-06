# 0.12.0 - 2018-12-03

* **Overhaul API to remove context object when no precomputation is needed**
* Add `ThirtyTwoByteHash` trait which allows infallible conversions to `Message`s
* Disallow 0-valued `Message` objects since signatures on them are forgeable for all keys
* Remove `ops::Index` implementations for `Signature`
* Remove depecated constants and unsafe `ZERO_KEY` constant

# 0.11.5 - 2018-11-09

* Use `pub extern crate` to export dependencies whose types are exported

# 0.11.4 - 2018-11-04

* Add `FromStr` and `Display` for `Signature` and both key types
* Fix `build.rs` for Windows and rustfmt configuration for docs.rs
* Correct endianness issue for `Signature` `Debug` output

# 0.11.3 - 2018-10-28

* No changes, just fixed docs.rs configuration

# 0.11.2 - 2018-09-11

* Correct endianness issue in RFC6979 nonce generation

# 0.11.1 - 2018-08-22

* Put `PublicKey::combine` back because it is currently needed to implement Lightning BOLT 3

# 0.11.0 - 2018-08-22

* Update `rand` to 0.4 and `gcc` 0.3 to `cc` 1.0. (`rand` 0.5 exists but has a lot of breaking changes and no longer compiles with 1.14.0.)
* Remove `PublicKey::combine` from API since it cannot be used with anything else in the API
* Detect whether 64-bit compilation is possible, and do it if we can (big performance improvement)

# 0.10.0 - 2018-07-25

* A [complete API overhaul](https://github.com/rust-bitcoin/rust-secp256k1/pull/27) to move many runtime errors into compiletime errors
* Update [libsecp256k1 to `1e6f1f5ad5e7f1e3ef79313ec02023902bf8`](https://github.com/rust-bitcoin/rust-secp256k1/pull/32). Should be no visible changes.
* [Remove `PublicKey::new()` and `PublicKey::is_valid()`](https://github.com/rust-bitcoin/rust-secp256k1/pull/37) since `new` was unsafe and it should now be impossible to create invalid `PublicKey` objects through the API
* [Reintroduce serde support](https://github.com/rust-bitcoin/rust-secp256k1/pull/38) behind a feature gate using serde 1.0
* Clean up build process and various typos


