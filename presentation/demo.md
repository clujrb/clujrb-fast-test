# Demo application

* Devise demo application
* 1 model, 3 controllers + unit tests
* 9 acceptance tests

* Rails 4.2, Bootstrap-Sass 3.3, RSpec 3.1, Capybara 2.4

- ```rails server```

# Springified RSpec

- ```git checkout springify```

> Gemfile:
> * gem "spring-commands-rspec"

> * bundle install

> Unspringified

- ```spring stop```
- ```time bundle exec rspec```

> Springify

- ```bundle exec spring binstub rspec```
- ```bin/rspec spec```
- ```spring status```

> Running springified RSpec will start up Spring server

- ```time bin/rspec spec```
- ```git reset --hard```

# Spring vs Zeus

- ```git checkout zeus-vs-spring```

> In tmux
- ```zeus start```
- ```time zeus rspec spec```

# The ninja setup

- ```git checkout zeus-guard```
- ```spring stop```
- restart Zeus

> Introducing guard to the equation

> Gemfile
> * guard-rspec
> * zeus

> Generated a Guardfile
> guard init rspec

- ```cat Guardfile```

> # Configure Guardfile

> In order to run it with guard:

> rspec_options = {
>  :cmd            => 'zeus rspec',
> }

> Watch clause; if I change any .rb file in app/ directory it will run its _spec.rb counterpart

> watch(%r{^app/(.+)\.rb$})  { |m| "spec/#{m[1]}_spec.rb" }

- ```guard```

# Why I'm moving away from Zeus

- sometimes messes up constant loading
- doesn't understand nesting of shared_examples
- Spring comes bundled with Rails >= 4.1

# Conclusion

- constant tweaking your workflow will make development faster
- play around & experiment with tools, it's really rewarding
