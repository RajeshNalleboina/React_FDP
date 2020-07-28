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

+ fetch method return a promise to the response to the request
+ fetch method has one argument is must and it is a path for the resourse file
+ it returns a response and it may be text or blob or json
+ We have to use a server(Here we are using a web server for chrome)

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

