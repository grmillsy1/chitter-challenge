if ENV['RACK_ENV'] != 'production'
  require 'rspec/core/rake_task'
  require 'data_mapper'
  require './app.rb'

  RSpec::Core::RakeTask.new :spec

  task default: [:spec]

  namespace :db do
    desc 'Non destructive upgrade'
    task :auto_upgrade do
      DataMapper.auto_upgrade!
      puts "auto_upgrade complete (no data loss)"
    end

    desc 'destructive upgrade'
    task :auto_migrate do
      DataMapper.auto_migrate!
      puts 'Auto-migrate complete (data was lost)'
    end

  end

end
