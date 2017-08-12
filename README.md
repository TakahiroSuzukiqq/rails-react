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
  
# Reference    
  Japanese only: [react-railsを使ってReactのTutorialをやってみる](http://qiita.com/joe-re/items/96f12dda4a62470d1d7c)     
  Japanese only: [一人React.js Advent Calendar 2014](http://qiita.com/advent-calendar/2014/reactjs)    
  
