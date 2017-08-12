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
$ rails g controller api/v1/comments --no-assets  (for API controller, so no need to create js and stylesheet)    
$ rails g model comment author:string text:text (create Model to access db and to receive json)  
$ rake db:migrate
````  
  
# Reference    
  Japanese only: [react-railsを使ってReactのTutorialをやってみる](http://qiita.com/joe-re/items/96f12dda4a62470d1d7c)     
  Japanese only: [一人React.js Advent Calendar 2014](http://qiita.com/advent-calendar/2014/reactjs)    

# Issues warnings   
  ````  
  Uncaught ReferenceError: $ is not defined  
  ````  
    
  [stack overflow Uncought Reference Error: $ is not defined?](https://stackoverflow.com/questions/2075337/uncaught-referenceerror-is-not-defined)  

          
  <a href="https://ibb.co/hqbWRa"><img src="https://image.ibb.co/jPwnzv/Screen_Shot_2017_08_12_at_17_35_54.png" alt="Screen_Shot_2017_08_12_at_17_35_54" border="0"></a>  
      
     
       
  ````  
  Warning: Each child in an array or iterator should have a unique "key" prop.  
  => put 
  ````  
  [stack overflow : Warning: Each child in an array or iterator should have a unique "key" prop.](https://stackoverflow.com/questions/34576332/warning-each-child-in-an-array-or-iterator-should-have-a-unique-key-prop-che)    
  [unique key related warning: Japanese](http://h3poteto.hatenablog.com/entry/2016/01/03/013921)  

        
  <a href="https://ibb.co/cxkEev"><img src="https://image.ibb.co/naSSzv/Screen_Shot_2017_08_12_at_17_49_33.png" alt="Screen_Shot_2017_08_12_at_17_49_33" border="0"></a>  
      
  <a href="https://ibb.co/nEXwRa"><img src="https://image.ibb.co/ickGRa/Screen_Shot_2017_08_12_at_18_11_15.png" alt="Screen_Shot_2017_08_12_at_18_11_15" border="0"></a>  
    


      