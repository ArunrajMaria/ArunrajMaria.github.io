<!DOCTYPE html>
<html>
<head>
<title>Navigation system</title>
</head>
   <style>
      #map {
        height: 100%;
      }
       html, body {
        height: 100%;
        margin: 0;
        padding: 0;
      }
      #right-panel {
        font-family: 'Roboto','sans-serif';
        line-height: 30px;
        padding-left: 10px;
      }

      #right-panel select, #right-panel input {
        font-size: 15px;
      }

      #right-panel select {
        width: 100%;
      }

      #right-panel i {
        font-size: 12px;
      }
      #right-panel {
        height: 100%;
        float: right;
        width: 390px;
        overflow: auto;
      }
      #map {
        margin-right: 400px;
      }
      @media print {
        #map {
          height: 500px;
          margin: 0;
        }
        #right-panel {
          float: none;
          width: auto;
        }
      }    
    </style>
</head>
<body onload="startingfn()">

<div id="right-panel">
 

<p>Click the "Book now" button to check & book nearest parking location</p>

<button onclick="dummy()" id="go">Book now</button>
<p id="demo"><p>
<p id="demo_2"><p>      
</div>

 <div id="map"></div>
 
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
 
<script type="text/javascript" >

var User_lat;
var User_lon;
var TT_slot;
var OBS_slot;
var TT_lock;
var OBS_lock;
var Dist_TT;
var Dist_OBS;
var Dest_lat,Dest_lon;
var TT_lat=12.971402;
var TT_lon=79.138078;
var OBS_lat=12.922310;
var OBS_lon=79.131966;
var flag=1;
var city_name;
var Origin_A,Destination_A;

function dummy()
{
for (var k=0;k<1000;k++){}
}

function startingfn()
{
get_location();
setTimeout(getUpdates,10000);
}


function get_location() {
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition);
    } 
	else { 
        alert.log("Geolocation is not supported by this browser.");
    }
	function showPosition(position) {
    User_lat =position.coords.latitude ; 
    User_lon= position.coords.longitude;
	    console.log("Location obtained");
            $.getJSON('https://maps.googleapis.com/maps/api/geocode/json?latlng='+ User_lat + ',' + User_lon +'&sensor=false',function(data_1) {
			
			for(var i=1;i< 6;i++){
				if(data_1.results[0].address_components[i].types[0]=='administrative_area_level_2')
				{
								var x=data_1.results[0].address_components[i];
				city_name=x.short_name;
				document.getElementById('demo_2').innerHTML ="You are in ";
				document.getElementById('demo_2').innerHTML +=city_name;
				break;
				}
				}	
	});
}


	}

function getUpdates() {
			$.getJSON('https://api.thingspeak.com/channels/431927/fields/1/last.json', function(data_2) {
			TT_slot=Number(data_2.field1);
			console.log('TT_slot');
			});
			$.getJSON('https://api.thingspeak.com/channels/431927/fields/2/last.json', function(data_3) {
			OBS_slot=Number(data_3.field2);
			console.log('OBS_slot');
			});
			$.getJSON('https://api.thingspeak.com/channels/431927/fields/3/last.json', function(data_4) {
			TT_lock=Number(data_4.field3);
			console.log('TT_lock');
			});
			$.getJSON('https://api.thingspeak.com/channels/431927/fields/5/last.json?callback=?', function(data_5) {
			OBS_lock=Number(data_5.field5);
			console.log('OBS_lock');
			});
			
			
			
		}	

function initMap(){
			var x="TT_slot="+TT_slot+" OBS_slot="+OBS_slot+" TT_lock="+TT_lock+" OBS_lock="+OBS_lock;
		console.log(x);

if(city_name=='Vellore' || city_name=='vellore')
{
			console.log("You are in Vellore");
console.log("Intializing map");
var start=User_lat+","+User_lon;
destinationA=TT_lat+","+TT_lon;
destinationB=OBS_lat+","+OBS_lon;

var service = new google.maps.DistanceMatrixService();
service.getDistanceMatrix(
  {
    origins: [start],
    destinations: [destinationA, destinationB],
    travelMode: 'DRIVING'}, report);

function report(response, status) {
  if (status == 'OK') {

      var results = response.rows[0].elements;
        Dist_TT = Number(results[0].distance.value);
		Duration_TT=Math.ceil((Number(results[0].duration.value))/60);
		Dist_OBS=Number(results[1].distance.value);
		Duration_OBS=Math.ceil((Number(results[1].duration.value))/60);
		document.getElementById("demo").innerHTML="Distance to TT: "+Dist_TT+"m; Distance to OBS: "+Dist_OBS+"m;";}}

setTimeout(check_condition,20000);
		
function check_condition(){
if(TT_lock==1 && OBS_lock==1){
alert("Both were booked...NO SPACE available");
}
		
else if(TT_lock==0 && OBS_lock==0){
if (TT_slot==0 && OBS_slot==0)
{
flag=-1;
show_map();
}
else if(TT_slot==0 && OBS_slot==1)
{
flag=1;
Dest_lat=OBS_lat;
Dest_lon=OBS_lon;
document.getElementById('demo').innerHTML +="\nNearest available parking location is Old Bus stand,Vellore";
show_map();
setTimeout(Book_OBS,10000);
}
else if(TT_slot==1 && OBS_slot==0)
{
flag=1;
Dest_lat=TT_lat;
Dest_lon=TT_lon;
document.getElementById('demo').innerHTML ="\nNearest available parking location is Technology Tower,VIT";
show_map();
setTimeout(Book_TT,10000);
}
else if(TT_slot==1 && OBS_slot==1){
flag=1;
 
  
if(Number(Dist_TT) > Number(Dist_OBS))
{
Dest_lat=OBS_lat;
Dest_lon=OBS_lon;
document.getElementById('demo').innerHTML +="\nNearest available parking location is Old Bus stand,Vellore";
show_map();
setTimeout(Book_OBS,10000);
}
else if(Number(Dist_TT) < Number(Dist_OBS))
{
Dest_lat=TT_lat;
Dest_lon=TT_lon;
document.getElementById('demo').innerHTML +="\nNearest available parking location is Technology Tower,VIT";
show_map();
setTimeout(Book_TT,10000);
}
else
{
flag=-1;
alert("Errror in calculating distance. Try again");}  
}

}



else if(TT_lock==1){
if(OBS_slot==1){
flag=1;
Dest_lat=OBS_lat;
Dest_lon=OBS_lon;
document.getElementById('demo').innerHTML +="\nNearest available parking location is Old Bus stand,Vellore";
show_map();
setTimeout(Book_OBS,10000);
}
else if(OBS_slot==0){
alert("No spaces");
}
}

else if(OBS_lock==1){
if (TT_slot==1){
flag=1;
Dest_lat=TT_lat;
Dest_lon=TT_lon;
document.getElementById('demo').innerHTML ="Nearest available parking location is Technology Tower,VIT";
show_map();
setTimeout(Book_TT,10000);
}
else if(TT_slot==0)
{
alert("No spaces");
}
}
}
}


else if(!(city_name=='Vellore' || city_name=='vellore'))
{
alert("You are out of  vellore city");
}
}



function show_map(){
if(flag==-1){
document.getElementById('demo').innerHTML ="Sorry,Currently NO SPACE available";
console.log("Sorry,Currently NO SPACE available");
}
else {
	var start=User_lat+","+User_lon;
	var end=Dest_lat+","+Dest_lon;
	
        var directionsDisplay = new google.maps.DirectionsRenderer;
        var directionsService = new google.maps.DirectionsService;
        var map = new google.maps.Map(document.getElementById('map'), {
          zoom: 10,
          center: {lat: 12.93, lng: 79.12}
        });
		calculateAndDisplayRoute(directionsService, directionsDisplay);
        directionsDisplay.setMap(map);
        directionsDisplay.setPanel(document.getElementById('right-panel'));        

      function calculateAndDisplayRoute(directionsService, directionsDisplay) {
        directionsService.route({
          origin: start,
          destination: end,
          travelMode: 'DRIVING'
        }, function(response, status) {
          if (status === 'OK') {
            directionsDisplay.setDirections(response);
          } else {
            window.alert('Directions request failed due to ' + status);
          }
        });
      }
}
}

function Book_TT()
{
var ref='Your booking id=';
	ref+=Math.floor(Math.random() * 1000) + 1;
	alert(ref);
$.getJSON('https://api.thingspeak.com/update.json?api_key=826FDB8WEJMG9LC3&field3=1&field4='+Duration_TT, function(data_6) {});
console.log('TT booked');
}

function Book_OBS()
{
var ref='Your booking id=';
	ref+=Math.floor(Math.random() * 1000) + 1;
	alert(ref);
$.getJSON('https://api.thingspeak.com/update.json?api_key=826FDB8WEJMG9LC3&field5=1&field6='+Duration_OBS, function(data_6) {});
console.log('OBS booked');
}

</script>
 
<script>
var url = "https://maps.googleapis.com/maps/api/js?key=AIzaSyAUoevmPug-V3btHPVB_HtbSnODcuICj9A&callback=initMap";
$( "#go" ).click(function(){
$.getScript( url, function() {
console.log("Finished");
});
});
</script>

</body>
</html>