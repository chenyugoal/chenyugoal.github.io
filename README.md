# About

https://chenyugoal.github.io/

Chenyu's personal website, adapted from [Hydejack](https://hydejack.com/)


Run locally with the existing dependency lockfile (verified with Ruby 2.7.6 and
Bundler 2.2.19). With Ruby 2.7.6 installed through rbenv:

```bash
rbenv local 2.7.6
rbenv exec gem install bundler -v 2.2.19
rbenv exec bundle _2.2.19_ install

rbenv exec bundle _2.2.19_ exec jekyll serve --host 127.0.0.1 --port 4000
```
