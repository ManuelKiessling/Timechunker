$LOAD_PATH.unshift File.expand_path("../lib", __FILE__)

require "rake/testtask"
require "timechunker/version"

desc "Default: run tests"
task :default => :test

desc "Run tests."
Rake::TestTask.new(:test) do |t|
  t.libs << "lib"
  t.libs << "test"
  t.pattern = "test/**/*_test.rb"
  t.verbose = true
end

desc "Build a gem from gemspec"
task :build do
  system "gem build timechunker.gemspec"
end

desc "Release new gem version"
task :release => :build do
  system "gem push timechunker-#{Timechunker::VERSION}"
end
