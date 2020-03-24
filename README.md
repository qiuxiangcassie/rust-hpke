rust-hpke
=========

This is an work-in-progress implementation of the [HPKE](https://datatracker.ietf.org/doc/draft-irtf-cfrg-hpke/) hybrid encryption standard. Once this is passing official known-answer tests, I'll publish it as a crate.

What it implements
------------------

Currently, all of draft02 functionality is implemented, besides the single-shot API. In addition, the exporter API is implemented.

Not many algorithms are currently supported. Here's what we have:

* KEMs
    * DHKEM(Curve25519)
* KDFs
    * HKDF-SHA256
* AEADs
    * AES-GCM-128
    * AES-GCM-256
    * ChaCha20Poly1305

**THIS IMPLEMENTATION IS NOT KNOWN TO COMPLY WITH ANY STANDARDS...YET**

Crate Features
--------------

* This crate does support `no_std`. However, the `std` feature is enabled by default.

For info on how to omit or include feature flags, see the [cargo docs on features](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html#choosing-features).

Tests
-----

To run tests, execute `cargo test`. This includes known-answer tests, which test against `test-vector-COMMIT_ID.json`,where `COMMIT_ID` is the short commit of the [reference implementation](https://github.com/bifurcation/hpke) version that created that test vector. Please see the reference implementation for information on how to generate a test vector.

Currently, file `test-vector-modified.json` is derived from a modified version of the reference implementation. Once the necessary changes are made upstream, the file will be updated.

What's next
-----------

- [ ] Implement one-shot API
- [ ] Add support for more KEMs and KDFs

License
-------

Licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE))
 * MIT license ([LICENSE-MIT](LICENSE-MIT))

at your option.

Warning
-------

This code has not been audited in any sense of the word. Use at your own discretion.
