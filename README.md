# Bible

This is a Bible app targeting linux mobile operating systems.

### Setup

This project was initialized to target linux and web

    clj -M:cljd init --platforms linux,web

### Install Dependencies

TODO: I don't remember what all I needed to install to get things set up.
Definitely these, but possibly more:
- [Clojure CLI](https://clojure.org/guides/install_clojure)
- [ClojureDart](https://github.com/Tensegritics/ClojureDart)

### Development

    clj -M:test:spec    # Run all tests
    clj -M:watch        # Run the app and watch for changes
