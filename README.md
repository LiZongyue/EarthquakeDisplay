# Java.coursera

A Start-Project with Java

1.HelloWorld.Java
--------------------------------
The first mini project was developed for the sake of getting familiar with the library Processing and UnfoldingMap package offered by FH Potsdam。
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
7. different objects such as circles with color and texts are drawn as a Key in the canvas provided by PApplet／
% In ArrayList, the add method returns a value of datatype boolean. If there is no boolean value which receives the returned value, it's also ok.
