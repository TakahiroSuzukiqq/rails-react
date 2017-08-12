# Description  
  This is an Ruby on rails API using React. A gem called ` gem 'react-rails'` enables to write React syntax to create components and by rendering them, created GET(access to the db) and POST(create API by submitting text) methods.  
  You can see JSON formatted data by accessing `localhost:3000/api/v1/comments.json`.   
  (*Following turorial is written in Japanese.) 　　  
    
  <a href="https://ibb.co/ksodNF"><img src="https://image.ibb.co/hHTOpv/Screen_Shot_2017_08_12_at_22_30_03.png" alt="Screen_Shot_2017_08_12_at_22_30_03" border="0"></a>  

          
   
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
* create GET and POST function  
````  
     
        
            
# Reference   
  [REACT official tutorial](https://facebook.github.io/react/tutorial/tutorial.html)   
  [react-rails](https://facebook.github.io/react/tutorial/tutorial.html)  
  Japanese only: [react-railsを使ってReactのTutorialをやってみるby joe-re Edited at 2016-11-18](http://qiita.com/joe-re/items/96f12dda4a62470d1d7c)     
  Japanese only: [一人React.js Advent Calendar 2014 by koba04](http://qiita.com/advent-calendar/2014/reactjs)    
  [joe-re's Github](https://github.com/joe-re/react-rails-tutorial)   
  [Medium clone built with Ruby on Rails by kenny-hibino](https://github.com/kenny-hibino/stories)  
  [Integration of React + Webpack + Rails to build Universal (Isomorphic) Apps by shakacode](https://github.com/shakacode/react_on_rails)    
  [webpackを使った Rails上でのReact開発 by Mr. Haga Edited at 2016-07-27](http://techlife.cookpad.com/entry/2016/07/27/101015)     
         
             
# Issues warnings   
  
  ## Uncaught ReferenceError: $ is not defined    
    
  [stack overflow Uncought Reference Error: $ is not defined?](https://stackoverflow.com/questions/2075337/uncaught-referenceerror-is-not-defined)  

          
  <a href="https://ibb.co/hqbWRa"><img src="https://image.ibb.co/jPwnzv/Screen_Shot_2017_08_12_at_17_35_54.png" alt="Screen_Shot_2017_08_12_at_17_35_54" border="0"></a>  
      
     
       
  ## Warning: Each child in an array or iterator should have a unique "key" prop.   
    
  [stack overflow : Warning: Each child in an array or iterator should have a unique "key" prop.](https://stackoverflow.com/questions/34576332/warning-each-child-in-an-array-or-iterator-should-have-a-unique-key-prop-che)    
  [unique key related warning: Japanese](http://h3poteto.hatenablog.com/entry/2016/01/03/013921)  

        
  <a href="https://ibb.co/cxkEev"><img src="https://image.ibb.co/naSSzv/Screen_Shot_2017_08_12_at_17_49_33.png" alt="Screen_Shot_2017_08_12_at_17_49_33" border="0"></a>  
      
  <a href="https://ibb.co/nEXwRa"><img src="https://image.ibb.co/ickGRa/Screen_Shot_2017_08_12_at_18_11_15.png" alt="Screen_Shot_2017_08_12_at_18_11_15" border="0"></a>     
      
        
          
## Uncaught TypeError: React.findDOMNode is not a function.        
  In the CommentForm component, I got the above error with below code so just changed another following code.      
  ````    
  var CommentForm = React.createClass({  
  handleSubmit: function(e) {  
    e.preventDefault();  
    var author = React.findDOMNode(this.refs.author).value.trim();  
    var text = React.findDOMNode(this.refs.text).value.trim();  
    if (!text || !author) {  
      return;  
    }  
    this.props.onCommentSubmit({author: author, text: text});   
    React.findDOMNode(this.refs.author).value = '';   
    React.findDOMNode(this.refs.text).value = '';   
    return;   
  },   
  ~~~~
  ````      
  ````      
  var CommentForm = React.createClass({   
  handleSubmit: function(e) {   
    e.preventDefault();    
    var author = ReactDOM.findDOMNode(this.refs.author).value.trim();    
    var text = ReactDOM.findDOMNode(this.refs.text).value.trim();    
    if (!text || !author) {    
      return;    
    }    
    this.props.onCommentSubmit({author: author, text: text});    
    ReactDOM.findDOMNode(this.refs.author).value = '';    
    ReactDOM.findDOMNode(this.refs.text).value = '';    
    return;    
  },    
  ~~~~
  ````   
  <a href="https://ibb.co/j58g9v"><img src="https://image.ibb.co/nJ2mba/Screen_Shot_2017_08_12_at_22_50_10.png" alt="Screen_Shot_2017_08_12_at_22_50_10" border="0"></a>  

          
      
          