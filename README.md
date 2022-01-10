# Archive Your e621 Favorites Offline

Monosodium is a tool that will archive your e621 favorites offline.  If you
don't know what e621 is, don't ask.

## Building

This project is written in Rust and uses the Rust build tools to compile.
The easiest way to get started with Rust is via rustup:

- https://rustup.rs

To build:

    cargo build --release

The output binary will be `./target/release/monosodium`

## Usage

    monosodium --user-id <USER-ID> --directory <DIR> [--progress]

The first argument is a *numeric* user id, which you can find from your e621
profile page.

The second argument is a local directory where your favorites will be
downloaded and stored. Metadata about the downloaded posts will be stored in
JSON files in a subdirectory of this directory, named `metadata`.

The last argument is an optional flag that will enable more verbose progress
output when iterating over favorites pages.

## Known Limitations

Downloading can be slow because it is done serially, one request per second,
in order to comply with the API requirements of the e621 site. Downloading
faster is possible, but it would put more stress on e621, and we want to be
good Internet citizens.

# License

See the file `LICENSE.txt` for details.
