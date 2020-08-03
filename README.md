# Bootstrap4:
  ==============

+ Bootstrap is the most popular front end framework to build responsive websites faster and easily
+ It includes html,css based design templates and optional js plugins(jquery and popper js files)
+ It is compatable with all moder browsers


# Colors:
=========
  class       |  color
  ------------|--------
   primary      |  blue
   secondary    |  gray 
   info | sky blue
   success | green
   warning | orange
   dange | red
   dark | black
   light |  text as light gray(white background)
   white |  text as white (white background)


# Gird system:
==============

+ Gridsystem involve main role for responsiveness of an application
+ Grid system has 5 default classes with respective devices to achieve responsive of a web page
+ 12 columns for each row in a page

    .         | Exatra small  (<576px) | small    (>=576px)   |Medium  devices (>=768px)  |  Large devices  (>=992px)   |Extra large devices (>=1200px)
    ------------------| -----------------------|----------------------|---------------------------|-----------------------------|-------------------------------         
    class prefix      | .col                   |         .col-sm      |           .col-md         |     .col-lg                 |.col-xs     
    No of columns  |12|12|12|12|12

# Tables:
==========
 - .table table-bordered
    - table-striped
    - table-dark
    - thead-dark
    - table-hover
    - table-borderless
 - We can apply contextual class for table
    
    
# JSON:
  + **JSON** - JavaScript Object Notation
  + Json mainly used to store and transfer data between the webapplications and servers
  + JSon filename extension is **.json**
  + Json data is a pair of key and value( Key is a string,value is any datatype)
  + Data should be separated by cammas
 
### JSON Datatypes:
===================
+ Number
+ String
+ Object
+ Array
+ Boolean
+ Null

Example:
========
```
{
	"profile":{
		"name":"Kalyan",
		"Age":25,
		"Collegues":["Sam","Ankith","Jack"],
		"Education":{
			"SSC":"St.Marys High School in Vijayawada",
			"Inter":"Nri junior college at guntur",
			"B.tech":"Universal college"
		}
	}
}
```

# Fetch API:
=============

+ fetch method return a promise to the response to that request
+ fetch method has one argument is must and it is a path for the resourse file
+ it returns a response and it may be text or blob or json
+ We have to use a server(Here we are using a web server for chrome)


Example for response text:
==========================
```
fetch('data.txt')
.then(response=> response.text())
.then(function(data){
	console.log(data);
})
```
Example for fetch blob(image):
===============================
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>
<img src="" id="image1">
<script type="text/javascript">
	fetch('images/admin.png').then(
		function(response) {
	// return response.blob()
	console.log(response);
	return response.blob();
}).then(blob =>{
	console.log(blob);
	document.getElementById("imkage1").src=URL.createObjectURL(blob);
}).catch(error=>{
	console.error(error);
	console.log("error!");
})
</script>
</body>
</html>
```
Example for fetch json to html page:
====================================
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>
<img src="" id="image1">
<div class="main">
	<div class="left">
		
	</div>
	<div class="right">
		
	</div>
</div>
<script type="text/javascript">
	fetch('data.json').then(
		function(response) {
	// return response.blob()
	console.log(response);
	return response.json();
}).then(data =>{
	console.log(data);
	profile(data.profile)
}).catch(error=>{
	console.error(error);
	console.log("error!");
})

var main=document.querySelector('.main');
var left=document.querySelector('.left');

var profile= function (info){

	var h2=document.createElement("h2");
	h2.textContent=info.name;
	left.appendChild(h2);
}

	main.appendChild(left);
</script>
</body>
</html>
```

# forEach and map functions

+ Both are applicable for arrays
### foreach:
+ the data can return in the form of normal elements ,when array is not const
```
 let myAwesomeArray = [1, 2, 3, 4, 5]
myAwesomeArray.forEach(x =>console.log( x*2))

o/p: 2
4
6
8
10
```
+ If array is const foreEach returns undefined
```
 const myAwesomeArray = [1, 2, 3, 4, 5]
const demo=myAwesomeArray.forEach(x => x*2)
console.log(demo);
o/p: is undefined
```

## map:
=======
+ If array is const map returns new array with transmission of data
```
 const myAwesomeArray = [1, 2, 3, 4, 5]
const demo=myAwesomeArray.map(x => x*2)
console.log(demo);
```


#Props :
========

+ Props is like arguments in function
+ Props can be passed from parent component to child component(uni directional flow)
+ Data from props is read only

## props with Finctional component:
===================================
+ letus consider Banks as parent Component,  Andhra(func) and Corp(class) as ChildComponent

Banks.js:
=========
```
import React from 'react';
import Andhra from './Andhra';
import Corp from './Corp';

const Banks = () =>{
return (
	<div>
	<h1>Banks is a Parent Component</h1>

       <Andhra name="Andhra bank"/>
       <Corp name="Corporation Bank" />
	</div>);
}

export default Banks;
```

Andhra.js:
=========
```
import React from 'react';

const Andhra =(props)=>{
	console.log(props.name);
	return <div> 
	
	<h2>Name is:{props.name}</h2>

	</div>
}

export default Andhra;
```
Corp.js:
========
```
import React,{Component} from 'react';


class Corp extends Component{
          
         render(props){
                // console.log(this.props);
         	return (

         		<div>

                   {this.props.name}
         		</div>);
         }
}

export default Corp;

```
