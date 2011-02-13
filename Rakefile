require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "mongoid_paperclip_image_dimension"
  gem.homepage = "http://github.com/aq1018/mongoid_paperclip_image_dimension"
  gem.license = "MIT"
  gem.summary = %Q{A simple plugin to persist image dimensions into mongoid document.}
  gem.description = %Q{A simple plugin to persist image dimensions into mongoid document.}
  gem.email = "aq1018@gmail.com"
  gem.authors = ["Aaron Qian"]
  gem.add_runtime_dependency 'mongoid', '~> 2.0.0.beta.20'
  gem.add_runtime_dependency 'mongoid-paperclip', '~> 0.0.3' 
  
  gem.add_development_dependency 'database_cleaner'
  gem.add_development_dependency 'bson', '~> 1.2.1'
  gem.add_development_dependency 'bson_ext', '~> 1.2.1'
  gem.add_development_dependency 'rspec', '~> 2.3.0'
  gem.add_development_dependency 'yard', '~> 0.6.0'
  gem.add_development_dependency 'bundler', '~> 1.0.0'
  gem.add_development_dependency 'jeweler', '~> 1.5.2'
  gem.add_development_dependency 'rcov', '>= 0'
end

Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
  spec.rspec_opts = "--color --format progress"
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
  spec.rcov_opts = "--exclude ~\/.rvm,spec"
end

task :default => :spec

require 'yard'
YARD::Rake::YardocTask.new
