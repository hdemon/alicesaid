require "bundler/gem_tasks"
require 'sinatra/activerecord'
require 'sinatra/activerecord/rake'
require './lib/shesaid'
require './db/connection'

task :init do
  characters = YAML.load_file "characters.yml"
  characters.each do |c|
    character = SheSaid::Character.new do |char|
      char.name = c["name"]
      char.search_word = c["search_word"]
    end
    character.save
  end
end

task :crawl do
  SheSaid::Crawler.crawl
end