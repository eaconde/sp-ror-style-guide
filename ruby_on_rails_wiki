[http://rubyonrails.org/ '''Ruby on Rails'''] or simply '''Rails''', is a web application framework written in [https://en.wikipedia.org/wiki/Ruby_(programming_language) Ruby] by [https://en.wikipedia.org/wiki/David_Heinemeier_Hansson David Heinemeier Hanson "'''DHH'''"] extracted during his work at [https://basecamp.com/ Basecamp] with a project management tool of the same name.

__TOC__

== Configuration ==

* All initialization code (custom or otherwise) needs be in the ''config/initializers'' directory. Files located here are auto-loaded and are executed on application startup.

* Each gem needs to have its own serializer having the same name as the gem its initializing. For instance, devise.rb, will_paginate.rb, redis.rb, etc.

* If a gem has different configuration per environment, you may accordingly add each gem's settings for each environment. Environment configs can be found under ''config/environments''.

* Keys, tokens, database settings, email settings needs to be hidden and should never be exposed to the source code repositories. It is advised that these are instead replaced by environment variables and setup on the machine where it will be used. For instance:

 config.encryption_key = 'c4e0de8aadc6811d1248f0aa220e9fdc' <= # Bad
 config.encryption_key = ENV['ENCRYPTION_KEY']              <= # Good

 Or in a database config:

 default: &mysql
   adapter: mysql2
   username: <%= ENV['MYSQL_DB_USR'] %>
   password: <%= ENV['MYSQL_DB_PWD'] %>
   host: <%= ENV['MYSQL_DB_HOST'] %>
   port: <%= ENV['MYSQL_DB_PORT'] %>
 production:
   <<: *mysql
   database: mysql_database

* Keep other configuration files in YAML and stored in the ''config/'' directory.
Since Rails 4.2 YAML configuration files can be easily loaded with the new config_for method:

 Rails::Application.config_for(:yaml_file)


== Routing ==

== Controllers ==
=== Rendering ===

== Models ==
=== ActiveRecord ===
=== ActiveRecord Queries ===

== Migrations ==

== Views ==

== Internationalization ==

== Assets ==

== Mailers ==

== Active Support Core Extensions ==

== Time ==

== Bundler ==

== Managing processes ==

== Gems ==
=== Devise ===
=== CanCanCan ===
