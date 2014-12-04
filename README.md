# cljs-kickoff

A Leiningen template for minimal ClojureScript project with lein-cljsbuild
and lein-ring.

It's intended to be as small as possible - only use Ring, ClojureScript,
lein-cljsbuild, and lein-ring. Users are free to add any other libraries as
they like.

It has complete configuration for lein-cljsbuild. The plugin compiles .cljs
files so that Ring can immediately serve them, it also is configured to
compile and include them in build.

## Included packages

```
:dependencies [[org.clojure/clojure "1.5.1"]
               [org.clojure/clojurescript "0.0-2156"]
               [ring "1.2.1"]]
:plugins      [[lein-cljsbuild "1.0.2"]
               [lein-ring "0.8.10"]]
:hooks        [leiningen.cljsbuild]
```

## Usage

Create project:

```bash
lein new cljs-kickoff my-project
```

Up and running (with CLJS compilation):
```bash
cd my-project
lein ring server
```

Interactive developmnt:
```bash
# Shell 1 - start server:
cd my-project
lein ring server

# Shell 2 - cljsbuild will recompile cljs whenever the files change:
cd my-project
lein cljsbuild auto
```

Package and run from jar:
```bash
cd my-project
lein ring uberjar
java -jar target/my-project-0.1.0-SNAPSHOT-standalone.jar
```

## More resources

This project is intentionally minimal. There's plenty resources on ClojureScript
on the web. Feel free to take a look at the posts on my blog at
http://squirrel.pl/blog/tag/clojurescript/

# Change log

  0.1.6

  commit fe215135064467076a90bcb4d4c6005e098faa9f
  Merge: 0eeebf5 9e6ded2
  Date:   Thu Dec 4 05:41:13 2014 +0200

    Merge branch 'feature/dependencies-update' into develop

        Dependencies version update based on [lein-ancient "0.5.5"](https://github.com/xsc/lein-ancient) advices.
        Update version of :
          `clojure` to "1.6.0".
          `ring` to the latest.
          `lein-ring` to the latest.
          `clojurescript` to the latest.
          `lein-cljsbuild` to be compatible with `clojurescript` version.

        Other:
          `.gitignore` - added `.lein-*`.


## License

Copyright © 2012 Konrad Garus

Distributed under the Eclipse Public License, the same as Clojure.
