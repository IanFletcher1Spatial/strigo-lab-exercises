<head><base target="_blank"> </head>

#### 1\. Open FME Workbench
Open FME Workbench to start creating a workspace. To do this in Windows go to Start > FME Desktop 2021.0 > FME Workbench. In macOS, go to Applications > FME 2021.0 > FME Workbench.\
We will be using FME Workbench for the entirety of the tutorial series. FME Workbench is where you will author all of your workspaces.

#### 2\. Start a New Workspace
After FME Workbench opens, click on the New button to create a new workspace. The empty workspace is referred to as the "canvas." The canvas is where all of the objects in a workspace will be contained. If you have just installed FME, click on Close to exit Workbench Essentials, it can be accessed again via Help > Workbench Essentials.\
![WorkbenchOverview.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028azF)

#### 3\. Drag and Drop to Add Data
In your operating system's file manager, browse to the C:\FMEData2021\Resources\GettingStarted\Data folder. In the Data folder, click on the LocalAddresses.csv and drag it into FME Workbench.\
![AddCSV.gif](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028azK)

#### 4\. Introduction to the Add Reader Dialog
A reader is a way to "read" data into FME. Depending on the dataset you are planning on reading in, the parameters for the Add Reader dialog may change. Let's go over the Add Reader dialog and set our parameters for the LocalAddresses.csv file we just added.\
![ReaderOverview.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028azP)

*a. Format and Dataset*\
When dragging and dropping data into FME, the Format, and Dataset auto-populates. Depending on the format you will want to confirm that the Format is correct, as there may be different format types for the same format extension. For our example, the format should be CSV (Comma Separated Value).\
FME can also read different dataset types, like folders, compressed files (.zip, .tar, etc.), and web-based. For more information see the [Dataset Types Documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Workbench/Workbench/dataset_types.htm).

*b. Parameters*\
Each format has specific parameters that can be set. To check the parameters, click on the Parameter button, which will bring up the Format Parameters dialog. If the Parameters button has an exclamation point ( ! ) at the end of it; this means that there are mandatory parameters that need to be set. To learn more about your format's specific parameters you can click on the Help button in the Parameters dialog.\
![ParametersButton.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028azo)

If you are using FME 2020 or newer, there are no parameters to set with this dataset, as FME automatically takes the Latitude and Longitude values in the dataset, and assigns them to the x and y coordinate data type. With this change to the data type, we will see points when we view the data in the [next article](https://community.safe.com/s/article/getting-started-with-fme-desktop-view-data).  If you have time, explore the parameters.

*c. Coordinate System*\
FME is coordinate system aware, if FME can detect the dataset's coordinate system, the Coord. System section will say "Read from Source." If it cannot, it will say "Unknown." If you know the coordinate system, yet FME doesn't detect it, you can enter it into the Coord. System box.\
If you opened the parameters, click OK to return to the Add Reader dialog. Set the Coord. System to LL-WGS84 by typing it into the box. For more information about Coordinate Systems, see the [documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Coordinate_Systems/CoordSys/coord_sys_about.htm) or the [Coordinate Systems 101: The Basics](https://www.safe.com/blog/2020/11/coordinate-systems-101-basics/) blog post.\
![image](https://user-images.githubusercontent.com/4148929/121102420-5dfe8700-c7b2-11eb-9b50-da9f49fa4fcc.png)

*d. Workflow Options*\
[Workflow Options](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_QuickTranslator/Workbench/readers_adding.htm) dictate how the reader feature types appear on the canvas; you can think of a feature type as FME's version of a layer in a CAD file or sheet in an Excel workbook. "Individual" will have each layer represented as its own feature type and "Single Merged" will have all of the layers represented as one feature type.\
For this example, leave this set to Individual Feature Types and then click OK to finish adding the reader.\
![WorkflowOptions.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028b08)

#### 5\. Feature Type
Once you click OK on the Add Reader dialog, a reader feature type will appear on the canvas. A feature type defines the schema of the data being read as well as the layers the dataset possesses. This will be the start of the workspace that everything is built upon.\
For this example, CSV is the feature type name. If you want the reader feature type to reflect the name of the file, you can change this in the reader parameters when you add the data.\
![FeatureType.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028azZ)

#### 6\. Add Another Reader
We need to add one more reader to the canvas before we can get started. To add a second reader, click on the Reader button on the top menu bar. Enter Esri Shapefile as the Format, and then browse to the dataset using the ellipsis button. Find the water_service_area.shp file in the C:\FMEData2021\Resources\GettingStarted\Data folder. Clear the Coord. System parameter and then click OK. (The Coord. System will still have a value from when we added the CSV file).\
Optionally, you can drag and drop the file from your file browser; just be sure to drag the water_service_area.shp file and not one of the required Shapefile sidecar files.\
![EsriReader.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028aze)

#### 7\. Save Your Workspace
Click the save button and then leave your workspace open.\
![SaveButton.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7I&feoid=00N30000006n8wU&refid=0EM4Q0000028b0D)

#### 8. Click "Next"
