# Encoding: UTF-8

source 'https://rubygems.org'

group :development do
  gem 'yard-chef'
  gem 'guard'
  gem 'guard-foodcritic'
  gem 'guard-rspec'
  gem 'guard-kitchen'
end

group :test do
  gem 'rake'
  gem 'rubocop'
  gem 'foodcritic'
  gem 'rspec', '>= 3'
  gem 'chefspec', '>= 4'
  gem 'simplecov'
  gem 'simplecov-console'
  gem 'coveralls'
  gem 'fauxhai'
end

group :integration do
  gem 'serverspec', '>= 2'
  gem 'cucumber'
end

group :build do
  gem 'fpm-cookery'
  gem 'chef', '>= 12'
  gem 'berkshelf', '>= 4'
  gem 'test-kitchen'
  gem 'kitchen-vagrant'
  gem 'kitchen-localhost'
end
