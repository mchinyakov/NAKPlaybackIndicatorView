require 'bundler/setup'
require 'rubocop/rake_task'

Rubocop::RakeTask.new(:style)

Dir['Tasks/**/*.rake'].each do |path|
  load(path)
end

desc 'Run CI task'
task ci: %w(test:all style)

desc 'Run CI task for Travis CI'
task travis: :ci do
  system('sudo easy_install cpp-coveralls && coveralls')
end

task default: 'test:all'
