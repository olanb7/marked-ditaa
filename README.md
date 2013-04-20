# marked-ditaa

An augmentation to the marked package to support diagrams in markdown!

## Additions to normal marked

Enclosing an ascii diagram in `//diag//` tags creates a URL to a ditaa web server, and returns a image tag with the result of the ditaa request. For example:

    //diag//
    +-----------+  +-----------+
    //diag//

is converted to:

    <img src='http://localhost:8080/DitaaWeb/ditaa?ditaa=%2B-----------%2B%20%20%2B-----------%2B' />

which the ditaa servlet returns a PNG representation of. You can run your own ditaa service with the code here: https://github.com/athoune/Ditaa-web/.

### New options

The following options can be changed using `marked.setOptions({option:newVal})`:

- __ditaaWeb__: The location of the ditaa web server to call out to. Defaults to `http://localhost:8080/DitaaWeb/ditaa`
- __ditaaQuery__: The query for the ditaa web server. Defaults to `?ditaa=`.