require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "gitback"
    gem.summary = %Q{A simple ruby library for backing up files to git}
    gem.description = %Q{Provide a list of files and/or directories and gitback will copy them to your git repo, commit and push when there are changes.}
    gem.email = "brycethornton@gmail.com"
    gem.homepage = "http://github.com/brycethornton/gitback"
    gem.authors = ["Bryce Thornton"]
    gem.add_dependency "grit", ">= 2.0.0"
    gem.add_development_dependency "shoulda"
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
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
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "gitback #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
