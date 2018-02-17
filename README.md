# GeoCoordinates

<html>
<head></head>
<body>
<div id="googleMap" style="width:80%;height:400px;"></div>

<div id="x" style="width:100%;height:400px;"></div>

</body>
<script>




function getLocation() {
	
    if (navigator.geolocation) {
			navigator.geolocation.getCurrentPosition(showPosition);
    } else {
        console.log("Geolocation is not supported by this browser.");
    }
}


function showPosition(position) {
var myCenter = new google.maps.LatLng(position.coords.latitude,position.coords.longitude);
	var mapProp= {
    center:myCenter,
    zoom:15,
};
var map=new google.maps.Map(document.getElementById("googleMap"),mapProp);
var marker = new google.maps.Marker({position:myCenter});
  marker.setMap(map);
  
  var infowindow = new google.maps.InfoWindow({
    content: "Your current location"
  });
  infowindow.open(map,marker);
}


getLocation();
</script>

<script src="https://maps.googleapis.com/maps/api/js?key=********&callback=getLocation"></script>
</html>


https://console.developers.google.com/apis/credentials?project=api-project-486357328737&authuser=0

https://developers.google.com/maps/solutions/store-locator/clothing-store-locator
