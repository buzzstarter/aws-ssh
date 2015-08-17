AWSSH
-----

A tool that makes easy to ssh into AWS EC2 servers

There's a blog post at [theheartbit.com](http://theheartbit.com/ruby/sqlite/threadsafe/concurrency/2015/08/18/aws-ssh/)
with some useful examples of using it:

### Usage

```
$ gem install aws-ssh
$ bundle exec awssh --help

awssh - a tool that makes easy to ssh into AWS EC2 servers

Usage: awssh [hostname regex]

Examples:
  $ awssh prod.*app2
  ... will SSH into the instance and you will see:
  user@prod-rails-app4~$

  $ awssh --show-only --stack qa -u worker
  ... will show all instances registered in QA stack of Opsworks
  ssh worker@10.20.30.40        => MyApp QA - qa-rails-app
  ssh worker@10.20.30.41        => MyApp QA - qa-sidekiq

  # All hosts in one-line (suitable for CSSH):
  worker@10.20.30.40 worker@10.20.30.41

Options:
    -s, --stack        AWS OpsWorks Stack name regex. E.g: `-s prod` will match "Production" stack name
    -p, --profile      AWS config profile name. Default: profile set in .awssh file
    -r, --region       AWS region. E.g: us-east-1. Default: region set in .awssh file
    -u, --user         SSH username to use. Default: user set in .awssh file or current machine user
    -so, --show-only   Only show the matched hosts instead of ssh. Default: false
    -cs, --csensitive  Use case-sensitive for regex matching. Default: false
    -v, --verbose      Verbose mode. Default: false
    --help             Shows help
```

DEFAULT OPTIONS
---------------

Use the [.awssh](https://github.com/buzzstarter/awssh/blob/master/.awssh) as
template to set default options.

Contributing
------------

1. Fork it ( https://github.com/buzzstarter/awssh/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

License
-------

Please see [LICENSE](https://github.com/buzzstarter/awssh/blob/master/LICENSE) for licensing details.
