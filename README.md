# easyLocator


EasyLocator is a jquery plugin to load locations with Google Maps in any website using a google spreadsheet or an array of objects.

Dependencies : [markerclusterer](https://googlemaps.github.io/js-marker-clusterer/docs/reference.html) , [Jquery](https://jquery.com/)

Note: (The file markerclusterer.min.js in this repo, is a version modified, you can use it if you want)

Examples:

 1. [Basic example](http://saulburgos.com/apps/easylocator/simple.html)
 2. [Array of object](http://saulburgos.com/apps/easylocator/array.html)

Add easyLocator in your web

    <script src="easyLocator.js"></script>

How to use it.
--------------

1. Create a Google spreadsheet like [this](https://docs.google.com/spreadsheets/d/1GsuoK3XyWJoiie1eq0qrd-2DxRVSQ0Ut7DkGI23Gq0s/edit?usp=sharing) , columns names need to be the same.
2. Go to:  "file > publish to the web" and verify the following fields 

	![enter image description here](http://i.imgur.com/0GIrxtA.jpg?1) 
	
3. Copy the url and extract the spreadsheetId:

     Example: 
     
     docs.google.com/spreadsheets/d/**1QM92ghpvJpRBryStWI-PWcRhpBSsYPva4XCXUxieXNU**/pubhtml
     
     (bold text is the spreadsheetId)
     
4. Call easyLocator with your selector and pass your spreadsheetId and teh google maps apiKey

	$(*yourContainer*).**easyLocator**({
          spreadsheetId: '1QM92ghpvJpRBryStWI-PWcRhpBSsYPva4XCXUxieXNU',
          apiKey: 'YOUR GOOGLE MAP API KEY'
   	})

	*"youcontainer" must have height"*

5. Done.
	  

**Note:   before of using this plugin, you must insert the CSS and dependencies**

    <link rel="stylesheet" type="text/css" href="easyLocator.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
    <script src="markerclusterer.min.js"></script>


SpreadSheet columns:
--------------------

**title:**   Title of each locations, this will be use in the list.

**description:**  Description,it will only appear inside the infowindow.

**lat:**  Coordinate use by google maps (latitude).

**lng:**  Coordinate use by google maps (longitude).

**image:**  Image of your location.

**link:**  If you want add a link, it will appear after the description

**iconmarker:**  If you want to customize the icon marker, you can use a url. Size recommended 30x30 pixels (png,jpeg, jpg)

*The most important part  when you add a location  in your spreadsheet, are the coordinates (lat, lng) together describe the exact location of a place in Google map.*

*If you want to know these coordinates,  you can use [this example](http://jsfiddle.net/kjy112/QvNUF/), just drag the marker and you will see the coordinates lat, lng*

easyLocator properties:
-----------------------
**spreadsheetId (string):**  Google spreadsheetId 

**useMarkerCluster (boolean):**  If you want use the [cluster marker](https://googlemaps.github.io/js-marker-clusterer/docs/reference.html)

**markerClustererOptions (object):**  Marker clusterer options

**openInfowindowAfterClick (boolean):**  If you want open the infowindows after click on ine item in the list.

**myLocations (array objects):**  array of object with your locations instead of the Google Spreadsheed.

**showListOnDesktop (boolean):** If you want hide the left list items on desktop version, The map will get width 100% automatically
 
**itemListActiveCustomClass (string):** This class will be added in the parent item after a click. You can use it to customize the element.
         
**infoWindowCustomClass (string):** This class will be added in the infoWindow container. You can use it to customize the element.
 
 example array : 

    var data = [{
            title: '',
            description: '',
            image: '', 
            link: '',
            iconMarker: '',
            lat: 12.9232,
            lng: -85.9206
         }]

**afterCLick (function):** callback function after clicked on an item in the list or marker, you will get only one argument the location clicked

**mapType (string):** Identifiers for common MapTypes: 'HYBRID','ROADMAP','SATELLITE','TERRAIN'

**apiKey (string and Mandatory):** You need create an api key and put it here. Follow these [steps](https://developers.google.com/maps/documentation/javascript/get-api-key)

If you do not add the apiKey the map won't load and you will get this error:
![error api key](http://i.imgur.com/IRYSwVt.png?1)



**easyLocator is 100% free to use. If you're using easyLocator on a commercial project and feeling generous, consider a donation. Thanks :) !**

[![donate](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=QBMMNFS76EMYU)
---------


Additional Tool Paneek.net:
-----------------------

Do you want a create virtual tour for your business ? Check my service: [http://www.paneek.net/](http://www.paneek.net/)
