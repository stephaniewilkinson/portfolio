# frozen_string_literal: true

source 'https://rubygems.org'
git_source(:github) { |repo| "https://github.com/#{repo}.git" }

####
# Welcome to your project's Gemfile, used by Rubygems & Bundler.
#
# To install a plugin, run:
#
#   bundle add new-plugin-name -g bridgetown_plugins
#
# This will ensure the plugin is added to the correct Bundler group.
#
# When you run Bridgetown commands, we recommend using a binstub like so:
#
#   bin/bridgetown start (or console, etc.)
#
# This will help ensure the proper Bridgetown version is running.
####

# If you need to upgrade/switch Bridgetown versions, change the line below
# and then run `bundle update bridgetown`
gem 'bridgetown', '~> 1'
gem 'bridgetown-feed'

# Uncomment to add file-based dynamic routing to your project:
# gem "bridgetown-routes", "~> 1.1.0", group: :bridgetown_plugins

# Uncomment to use the Inspectors API to manipulate the output
# of your HTML or XML resources:
# gem "nokogiri", "~> 1.13"

# Puma is a Rack-compatible server used by Bridgetown
# (you can optionally limit this to the "development" group)
gem 'puma', '~> 6'
gem 'rubocop'

group :test, optional: true do
  gem 'minitest'
  gem 'minitest-profile'
  gem 'minitest-reporters'
  gem 'nokogiri'
  gem 'rails-dom-testing'
  gem 'shoulda'
end
