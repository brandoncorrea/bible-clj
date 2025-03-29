# Bible

This is a Bible app targeting linux mobile operating systems.

### Bible API

Bible Sourced by: https://bible-api.com/

Pipe to `jq` for pretty-printed curl results: `curl the-endpoint | jq`

    # List Versions
    curl https://bible-api.com/data

    # List Books
    curl https://bible-api.com/data/{version}
    curl https://bible-api.com/data/kjv

    # List Chapters
    curl https://bible-api.com/data/{version}/{book}
    curl https://bible-api.com/data/kjv/GEN

    # List Verses
    curl https://bible-api.com/data/{version}/{book}/{chapter}
    curl https://bible-api.com/data/kjv/GEN/1

    # Single Verse
    curl https://bible-api.com/{book}%20{chapter}:{verse}?translation={version}
    curl https://bible-api.com/genesis%201:1?translation=kjv

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
