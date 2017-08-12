# Basic setup and installation   
````  
$ rails new react-rails-tutorial --database=postgresql  
* Add gem 'react-rails', '~> 1.0'   
$ bundle install  
$ rails g react:install  
$ rails g react:component CommentBox  
$ rails g controller comments  
* Create index page and code `<%= react_component('CommentBox') %>`    
* Routing : `root 'comments#index'`  
````  
  
  