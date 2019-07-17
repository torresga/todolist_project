require "rake/testtask"
require 'bundler/gem_tasks'
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# Add a task to your Rakefile that lists every file in your project except those whose names begin with . and those that reside in a directory whose name begins with .

# Loop through the paths of ENV["PWD"] with Find
#   Output filename if it does not begin with .
#   If directory begins with .
#     ignore it

desc 'File inventory'
task :inventory do
  Find.find(ENV["PWD"]) do |path|
    if File.directory?(path)
      if File.basename(path)[0] == "."
        Find.prune
      end
    else
      puts path if File.basename(path)[0] != "."
    end
  end
end
