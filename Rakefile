require File.expand_path('../lib/emojipacks_twitch', __FILE__)

task :default => [:build_global]

task :build do
  EmojipacksTwitch.build
end

task :build_global do
  EmojipacksTwitch.build_global
end

task :build_subscriber do
  EmojipacksTwitch.build_subscriber
end

task :create_readme do
  emotes = YAML.load_file 'output/twitch-global.yml'
  puts ' | | | | '
  puts ':---|:---|:---|:---'
  emotes['emojis'].each_slice(4) do |row|
    items = row.map do |m|
      "![#{m['name']}](#{m['src']}) `:#{m['name']}:`"
    end
    if items.size < 4
      items_size = items.size
      (4 - items_size).times { items << nil }
    end
    puts items.join('|')
  end
end
