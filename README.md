# [bitcoincore.org](https://bitcoincore.org)

* Bitcoin Core project website's source code

## Directory structure

- [Bitcoin Core RPC](_doc/en)
- [IRC meetings](_posts/en/meetings)
- [static pages](_posts/en/pages)
- [blog articles](_posts/en/posts)
- [Bitcoin Core release notes](_releases)
- [Repository tools](contrib)
- [Zurich 2016](logs)

* File names format
  * "Y-m-d-title.md"
    * _Example:_ 2015-12-31-title.md

## Front Matter notes

* uses
  * multilingual setup | ALL files
* fields
  - `name:`
    - group name / UNIQUE article
    - SAME group name / EACH translation
      - _Exmaple:_ `october15-report`
  - `id:`
    - TODO: each article translation must have a unique ID
    - Use the language code + `-name` field. e.g. `en-october15-report`
  - `permalink:`
    - the must include the language code, end a trailing slash, e.g. `/en/2015/12/31/report/`.
  - `title:`
    - article's translated title 
  - `type:`
    - content type
      - _Example:_ `pages`, `posts`, `releases`, `meetings`, etc.
  - `layout:`
    - layout template
      - _Example:_ `page`, `post`, etc.
  - `lang:`
    - language code
      - _Example:_ `en`, `fr`, etc.

```
---
title: Short Title
name: short-title
layout: post
type: posts
lang: en
id: en-short-title
permalink: /en/2016/01/01/short-title
---
```

## how to build?

* -- based on -- [Jekyll](https://jekyllrb.com/)
* TODO: To build
locally, [install Ruby 3.1.2](https://gorails.com/setup) using system
packages, [rvm](https://rvm.io), [rbenv](https://github.com/rbenv/rbenv), or another method.
Then clone this repository and change directory into it:

    git clone https://github.com/bitcoin-core/bitcoincore.org.git
    cd bitcoincore.org

Install the `bundle` utility using the Ruby package manager, `gem`, and
then use `bundle` to install the rest of the Ruby packages needed to
build this site.  Note, depending on your system configuration, you may
need to run `gem` as the superuser by putting "sudo" followed by a space
before the `gem` command.  You shouldn't need to use `sudo` with the
`bundle` command.

    gem update --system
    gem install bundler
    bundle install

To preview the site (this will launch a tiny webserver on port 4000):

    bundle exec jekyll server --future

To simply build the site (output placed in the `_site` directory):

    bundle exec jekyll build --future

Note that the `--future` parameter is only required if you're adding any
pages dated in the future (such as prepared release announcements).

To test the site:

    bundle exec jekyll build --future --drafts --unpublished
    bundle exec htmlproofer --check-html --disable-external --url-ignore '/^\/bin/.*/' ./_site

The additional parameters to `jekyll build` ensure that all possible
pages are built and checked.

## References

* CURRENT website
  * 's theme == old version of [Minimal Mistakes theme][]

[minimal mistakes theme]: https://mmistakes.github.io/minimal-mistakes/
[mm docs]: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
[mm config]: https://mmistakes.github.io/minimal-mistakes/docs/configuration/
[mm content]: https://mmistakes.github.io/minimal-mistakes/docs/posts/
[mm js]: https://mmistakes.github.io/minimal-mistakes/docs/javascript/
