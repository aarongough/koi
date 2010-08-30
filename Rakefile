require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'

desc 'Default: run unit tests.'
task :default => :test

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "min-koi"
    gemspec.summary = "A Parser and compiler for the MinKoi language."
    gemspec.description = "A modular compilation toolchain for the MinKoi language."
    gemspec.email = "aaron@aarongough.com"
    gemspec.homepage = "http://github.com/aarongough/min-koi"
    gemspec.authors = ["Aaron Gough"]
    gemspec.rdoc_options << '--line-numbers' << '--inline-source'
    gemspec.extra_rdoc_files = ['README.rdoc', 'MIT-LICENSE']
    gemspec.add_dependency('treetop')
    gemspec.add_dependency('koi-vm')
    gemspec.executables << 'minkoi'
  end
rescue LoadError
  puts "Jeweler not available. Install it with: gem install jeweler"
end


desc 'Test MinKoi.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib/*.rb'
  t.libs << 'test'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end


desc 'Generate documentation for MinKoi.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'MinKoi'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README.rdoc')
  rdoc.rdoc_files.include('lib/**/*.rb')
  rdoc.rdoc_files.include('app/**/*.rb')
end