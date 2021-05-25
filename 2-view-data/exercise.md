<head><base target="_blank"> </head>

Continue working in the workspace from the previous exercise or open C:\FMEData2021\Resources\GettingStarted\Workspaces\GettingStarted-ViewData-Begin.fmwt

#### 1\. View Source Data
The data we added in the previous exercise can be viewed within FME Workbench. Since we have two datasets, we can view them at the same time. To do this, we need to run the workspace with feature caching enabled.\
On the top toolbar, click the drop-down arrow next to the Run button. In the drop-down menu, ensure that Feature Caching is enabled. Now when we run the workspace, the data will be cached along the way, and we can view those caches.\
![EnableFeatureCaching.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0I)

Now click on the Run button, the workspace will run and the data will be cached for each of the reader feature types.\
![FeatureTypeCaches.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0N)

#### 2\. View Cache
Now that the workspace has been run, a magnifying glass icon appears on the reader feature types; this indicates that the data has been cached and can now be viewed. First, let's view each dataset separately.\
Click on the magnifying glass icon to open up the CSV reader feature type in the Visual Preview window.\
![ClickOnCache.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0S)

Additionally, you can also skip the running the workspace step and just view the data. To do this, click on the reader feature type, and then in the pop-up menu, click View Source Data. Note that this option is not available for all datasets, such as a dataset being read from the web.\
![ViewSourceData.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0X)

#### 3\. Introduction to Visual Preview
There are three parts to viewing data using Visual Preview in FME. Each part allows the user to view their data in different ways. To use Visual Preview, ensure that the workspace has been run and then select an object to load. Note: If you clicked on the Magnifying Glass and Visual Preview opened but you don't see any of the following views, click the icons on the left-hand side to toggle them on (d).\
![VisualPreviewOverview.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0c)

*a. Table View*\
The Table view displays the dataset's visible attributes. These attributes can be sorted or searched to explore the data. To toggle this view, click on the Table button ![TableViewIcon.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0h) on the left-hand side of the window (d). Note that attributes cannot be edited in Visual Preview, editing attributes will be covered in the [later article](https://community.safe.com/s/article/getting-started-with-fme-desktop-modify-attributes).\
![TableView.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0m)

*b. Graphics View*\
If the dataset has a spatial component, graphic, geometry, or coordinate values (like latitude and longitude), Visual Preview will display the graphics or geometry in the Graphics View. If there are no graphics or geometry, this view will not be available. To toggle this view, click on the Graphics button ![GraphicsViewIcon.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0r)  on the left-hand side of the window (d). By default, background maps are turned off. For more information on background maps, see the [documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Workbench/Workbench/options-background-maps-WB.htm).\
![GraphicView.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b0w)

*c. Feature Information View*\
The Feature Information View is where any additional information about a feature can be found, including format-specific attributes and coordinate systems. To toggle this view, click the Show/Hide Feature Information Button ![FeatureInfoIcon.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b16) on the left-hand side of the window (d).\
![FeatureTypeView.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b11)

#### 4\. Explore CSV Data
With the CSV LocalAddresses open in the Visual Preview window, take a moment to explore the dataset. In the Table View, we have addresses and a latitude/longitude location. FME 2020 or newer, automatically turns the latitude and longitude into point data which can be seen in the Graphics View.

#### 5\. Explore water_service_area data
Now, view the water_service_area data in Visual Preview by clicking on the green magnifying glass on the reader feature type.\
![ViewWater.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b1B)

Looking at the Table View for water_service_area you can see that there is an area that has the STATUS of RED. We will use this information in the next article to filter the data based on the RED value.\
![WaterVP.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7N&feoid=00N30000006n8wU&refid=0EM4Q0000028b1G)

#### 6\. View Both Datasets Together
When you click on the magnifying glass to view data in Visual Preview, only one dataset loads at a time. If you want to view all the data together, click and drag a box around all objects you wish to view.

In the next exercise, after we filter the data based on the RED status, we will only select the points that fall within the selected water_service_area.

#### 7. Click "Next"
