require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "ruby-growl"
    gem.summary = "Pure-Ruby Growl Notifier"
    gem.description = <<-EOF
ruby-growl allows you to perform Growl notification via UDP from machines
without growl installed (for example, non-OSX machines).

What's Growl?  Growl is a really cool "global notification system for Mac OS
X".  See http://growl.info/

See also the Ruby Growl bindings in Growl's subversion repository:
http://growl.info/documentation/growl-source-install.php

ruby-growl also contains a command-line notification tool named 'growl'.  Where possible, it isoption-compatible with growlnotify.  (Use --priority instead of -p.)
EOF
    gem.email = "dylan@dylanmarkow.com"
    gem.homepage = "http://github.com/dmarkow/ruby-growl"
    gem.authors = ["Eric Hodel", "Dylan Markow"]
  end
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*_test.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/*_test.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  if File.exist?('VERSION')
    version = File.read('VERSION')
  else
    version = ""
  end

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "ruby-growl #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
