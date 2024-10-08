# Pixelforce Kit

Pixelforce Kit implements 

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'pixelforce_kit'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install pixelforce_kit

## Usage
add below code to deploy.rb
```ruby
require 'pixelforce_kit'
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/pixelforce_kit. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## supervisor support

The recipes for capistrano3 with supervisor support.   
Please use `process:supervisor:task` to invoke it.   
They relied on some capistrano plugins for some variables

* [**rvm**](https://github.com/capistrano/rvm) for `rvm_ruby_version`

Tweak some option for supervisor, the following value is default

```ruby
set :autostart, 'true'
set :autorestart, 'true'
set :logfile_maxbytes, '1GB'
set :logfile_backups, '10'
```

#### unicorn

Relied on unicornherder for supervisor monitoring.

#### puma

Get rid of capistrano-puma, and now generate puma config itself.

```ruby
set :puma_threads, [0, 1]
set :puma_workers, 2
```

## sysvinit support

Please use `process:sysvinit:task` to invoke it.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
