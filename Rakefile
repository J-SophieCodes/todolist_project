require "bundler/gem_tasks"
require "rake/testtask"
require "find"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

# desc 'Run tests'
# task :test do
#   sh 'ruby ./test/todolist_project_test.rb' # sh method run the ruby command
# end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List all project files'
task :list_files do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with . names
    puts name if File.file?(name)
  end
end