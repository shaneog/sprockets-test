## sprockets-rails SRI test app


#### Getting Started

My environment:

```shell
$ ruby -v
ruby 2.2.2p95 (2015-04-13 revision 50295) [x86_64-darwin14]
$ rails -v
Rails 4.2.4
$ gem -v
2.4.8
```

The following commands were run to set up this project:

```shell
$ rails new sprockets-test
$ cd sprockets-test
$ rails generate controller welcome index
```

#### To Reproduce

I tested under the `production` environment.


```shell
export RAILS_SERVE_STATIC_FILES=true
export SECRET_KEY_BASE=$(rake secret)

RAILS_ENV=production rake assets:precompile
RAILS_ENV=production bundle exec rails server
```

The helper (`javascript_include_tag`) does not output the asset integrity hash.
