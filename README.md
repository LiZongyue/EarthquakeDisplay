# Java.coursera

A Start-Project with Java, totally 5 modules

1.HelloWorld.Java
--------------------------------
The first mini project was developed for the sake of getting familiar with the library Processing and UnfoldingMap package offered by FH Potsdam.

Not much thing to do, but just added some code to display a Map of authour's location.

2.EarthquakeCityMap.java
--------------------------------
The second mini Project was developed in order to use the processing library to build a simple GUI. The aim of this project is to read the Earthquake data from a website [Earthquakes/USGS](https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/2.5_week.atom) and displays the earthquake in a visually Map drawn in the canvas provided by PApplet.

In this project

1. an object UnfoldingMap is instantiated, the created map uses the API provided by MicrosoftMap.
2. two ArrayLists are created which. One of them stores instance objects of SimplePointMarker which implements the Interface Marker provided by UnfoldingMap, another store instance objects of PointFeature which is a subclass of Feature also provided by UnfoldingMap.
3. Extracted the Information of earthquakes and stored them in the PointFeature ArrayList objectwise.
4. a method called createMarker is developed which defines the behavior of the relationship of SimplePointMarker and the parameter PointFeature of this method, then returns an instance object SimplePointMarker.
5. the Behavior is: extract the location and magnitude of the Earthquake stored in the PointFeature and instantiated an object of SimplePointMarker with the parameter of extracted location. Next step is based on the magnitude to assign different color and radius to the SimplePointMarker object which will be displayed in the map corresponds to its location.
6. iterated the ArrayList of PointFeature and for each step the method CreateMarker will be called and thus for each step the returned instantiated SimplePointMarker will be passed to the Markers in the ArrayList.
7. different objects such as circles with color and texts are drawn as a Key in the canvas provided by PApplet
% In ArrayList, the add method returns a value of datatype boolean. If there is no boolean value which receives the returned value, it's also ok.

3.Package Module4
--------------------------------

### file Introduction

In this package, there are totally five .java files.

They are as follows: 
1. CityMarker.java
2. EarthquakeMarker.java
3. LandQuakeMarker.java
4. OceanQuakeMarker.java
5. EarthquakeCityMap.java

The respectively iheritance relationships of them are as follows:
1. CityMarker extends SimplePointMarker
2. EarthquakeMarker extends SimpleMarker
3. LandQuakeMarker extends EarthquakeMarker
4. OceanQuakeMarker extends EarthquakeMarker
5. EarthquakeCityMap extends PApplet

### What to do

1. Find and open the starter code: You will find the starter code for this part of the project in the module4 package. Expand the module4 package in the package explorer and you will see 5 java files: EarthquakeCityMap.java , EarthquakeMarker.java , CityMarker.java , LandQuakeMarker.java , OceanQuakeMarker.java. You can open any of them by double-clicking on them. Make sure you are working on the files in the module4 package and don't peek ahead to the other packages. We recommend making sure all other files are closed in Eclipse so you don’t get confused which file you are working on.

#### Hint for part 1:
> In the data folder (which is at the same level as the src folder), you will also see a file named “city-data.json”. You don’t have to modify that file, but if your favorite city is not there, you can add it by editing the file. Just be sure to match the format and data of the other cities exactly!

2. Trace the starter code (starting in setup in EarthquakeCityMap.java), predict what happens when you run it, and then run it. IF YOU ARE WORKING OFFLINE: Don’t forget to change the value of the offline variable to true, otherwise you will get an error. Notice that the file EarthquakeCityMap.java implements most of the functionality that you worked on in the programming assignment for module 3, but it's not exactly the same. Are you surprised by what happens (or doesn't happen) when you run it?

3. Implement the isLand(Feature earthquake) method in EarthquakeCityMap. This method should return true if the location of the input earthquake is on land. It should also set the "country" property on the LandMarker to the country where the earthquake occurred. Otherwise, the location is in the ocean and the method should return false. You will test this method once you have implemented the next method.

#### Hint for part 3: 
> A location is on land if it is located in *some* country. So, you can loop through all countries and check if the location is in any one of them. You can (and should) use the helper method isInCountry() given in the file, which takes care of a lot of the work of isLand for you, including setting the "country" property of the earthquake PointFeature. There is not a lot of code to add for this part.

4. Implement the printQuakes() method in EarthquakeCityMap. This method should use System.out.println() to list each country for which there was 1 or more earthquakes and the number of earthquakes detected in that country. Then it should print out the number of quakes that were detected in the ocean. Note that this method is not trivial. You will have to calculate the number of earthquakes per country from the information you have available. As an aside: If you are running the applet with a large earthquake file/feed (e.g. 1.0+ Past week or 30 days), you might find that printQuakes takes a long time to run. Feel free to comment out the call to printQuakes() in setup once you get it working if you find this is the case.

5. Test isLand and printQuakes. To facilitate basic testing, we have included two tester input files (test1.atom and test2.atom) and two files that include the expected output (test1.out.txt and test2.out.txt) for each of these test files. All files are in the data folder. You will see lines in the starter code for setup() that you can uncomment in order to run with the tester files. (Uncomment 1 line at a time). You can run each test and compare them to the test output, which you can open in eclipse by double-clicking it in the package explorer. If both outputs match, it is likely that you have implemented both isLand and printQuakes correctly. Note that order and formatting does not have to match.


6. Complete the method definition for the draw() method in the CityMarker class. We suggest you use triangles to represent cities, but of course the exact shape and color is up to you. Then add the marker to your key (which you will need to modify as you change your earthquake markers). Your map should now look something like the image below.

#### Hint for part 6:
> Because you are no longer working in the PApplet class, you will need to use the PGraphics object for drawing. You can call the same methods you were calling when you were drawing on the PApplet, but you call them on the pg object. The arguments x and y should be used (and passed into your graphics calls) as the center of the Marker you are drawing. See the comments in the draw() method for an example of how to do this.

### What has been done

In Step 3, with the helper method 'isInCountry', the Earthquake can be determined whether it happened in the given Land. Its arguments are PointFeature which relates to Earthquake and Marker which associates with Country(Land). Thus we further implement the method Island to return a boolean value which indicates a binary result whether the earthquake has happened in a country or not, for every country which located in the file "countries.geo.json". 

Then Island is used to determine the protected boolean field isOnland. The PointFeatrue of the earthquake will be added in ArrayList which stores Earthquakes. But it will be added separately due to the result given by Islan, if it's true, a new object of LandquakeMarker will be instantiated and added as the parameter for .add, otherwise of OceanquakeMarker. In this procedure, isOnland is assigned with boolean value.

In step 4, the key is to compare the name property of 2 different types of markers by iterating them. 

In step 6, what should be concentrated on is that The line map.draw() tells the UnfoldingMap to redraw itself, making all classes that implement the Marker interface, like SimplePointMarker, to redraw itself, i.e. **call the draw(PGraphics pg, float x, float y) method**.
