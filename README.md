gem-reset
=========

Synchronizes Gemset With Bundle
-------------------------------

We use `gemsets` to avoid typing `bundle exec`.
Sometimes our gemsets get cruft in them from bundle changes.
This utility will sync them back up, ensuring your gemset matches your bundle.

Should be functionally equivalent to the `empty` dance:

```sh
  rvm gemset empty
  rvm gemset use global
  rvm gemset empty
  gem install bundler
  rvm gemset use foo
  bundle
```

Hopefully removing the extra gems is a bit faster than rebuilding them all.

WARNING
-------

This is a proof of concept. It forcefully rips out every gem that isn't in your bundle.
If you don't use rvm gemsets you probably don't want this.

