source "https://rubygems.org"

branch = ENV.fetch("SOLIDUS_BRANCH", "master")

if branch == "master" || branch >= "v2.0"
  gem "rails-controller-testing", group: :test
end

git_source(:github) do |repo_name|
  repo_name = "#{repo_name}/#{repo_name}" unless repo_name.include?('/')
  "https://github.com/#{repo_name}.git"
end

if branch == 'master' || branch >= "v2.3"
  gem 'rails', '~> 5.1.0' # HACK: broken bundler dependency resolution
elsif branch >= "v2.0"
  gem 'rails', '~> 5.0.0' # HACK: broken bundler dependency resolution
else
  gem "rails", '~> 4.2.0' # HACK: broken bundler dependency resolution
  gem 'rails_test_params_backport', group: :test
end

group :development, :test do
  gem "deface"
  gem "solidus"
  gem "puma"
  gem "sassc-rails", "~> 1.3.0"
  gem "sass-rails", "~> 5.0.7"
  gem "solidus_auth_devise", '~> 2.1.0'
  gem "solidus_support", "0.4.1"

  gem "pg"
  gem "mysql2"
  gem "sqlite3", "~> 1.4.4"
end

group :test do
  gem "database_cleaner"
  gem "factory_girl"
  gem "ffaker"
  gem "friendly_id", "5.4.2"
  gem "rspec-mocks", "~> 3.7.0"
  gem "rspec-rails", "~> 3.7.2"
  gem "timecop"
  gem "vcr", "3.0.3"
  gem "webmock", "~> 3.13.0"
  gem "selenium-webdriver"
  gem 'chromedriver-helper', require: false
end

gemspec
