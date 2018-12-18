require 'rake/testtask'
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << 'lib'
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List files'
task :list_files do
  Find.find("/Users/mm-mac/test/todolist_project") do |path|
    if FileTest.directory?(path)
      if File.basename(path)[0] == ?.
        Find.prune
      else
        next
      end
    else
      name = File.basename(path)
      puts name if File.file?(path) && name[0] != ?.
    end
  end
end

desc 'Run tests'
task :default => :test
