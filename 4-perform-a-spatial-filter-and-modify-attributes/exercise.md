<head><base target="_blank"> </head>

Since we want to know which customers are affected by the failed water pump, we will need to filter the customers based on their spatial relationship to the water_service_area with a RED status. After we have determined which customers are affected, we will need to clean up the attributes before we can write the data out.

Continue working in the workspace from the previous exercise or open the C:\FMEData2022\Resources\GettingStarted\Workspaces\GettingStarted-FilterAndModify-Begin.fmwt workspace.\
![PreviousOverview.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b3R)

#### 1\.  Add Another Transformer
Now that we have learned how to add a transformer let's add another one to determine which LocalAddress points fall into the boundary of the water_service_area that we selected with the Tester.\
Add a **SpatialFilter** transformer to the canvas by typing SpatialFilter on the canvas. Once it is added, connect the CSV reader feature type to the **Candidate** input port on the SpatialFilter, by clicking and dragging to make the connection. Then connect the Passed output port on the Tester to the Filter input port on the SpatialFilter.\
![ConnectSpatialFilter.gif](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b3W)\
It's ok if your connection lines are crossed, but if you want to fix them, either move the CSV reader feature type below the water_service_area one by clicking and dragging or right-click on the **Filter** input port and select **Move Down**.\
![MoveDown.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b3b)

#### 2\. Open the SpatialFilter Parameters
Double-click on the **SpatialFilter** transformer to open the parameters. There are a lot of parameters here, but we can accept the defaults. Basically, how this transformer works is every point feature that comes into the Candidate port will be tested to see if it falls within the boundary of the water_service_area, which is the Filter. If it does, it will go to the Passed output port. This is a good transformer to use if you want to select features that are within (or not within) a certain boundary. For more information on the SpatialFilter, see the [documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Transformers/Transformers/spatialfilter.htm).\
The only thing that needs to be changed in the SpatialFilter is unchecking **Merge Attributes**. This option will merge all the attributes from the points and the boundary, which we do not need. Click **OK** to close the SpatialFilter.\
![SpatialFilter.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b3g)\

#### 3\. Run the Workspace and Inspect the SpatialFilter
Run the workspace once more and inspect the Passed output port on the SpatialFilter by clicking the green magnifying glass.\
You should have 6,722 points output and should be in roughly the same shape as when we viewed the water_service_area in exercise 2.\
![SpatialFilterOutput.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b3q)

#### 4\. Clean Up Attributes with an AttributeManager
The final step before we can write out the data is to clean up the attributes. There are several different transformers you can use to manage attributes, but the best one is the **AttributeManager** transformer. The AttributeManager allows you to add, delete, rename, and re-order your attributes. For more information on the AttributeManager, see the [documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Transformers/Transformers/attributemanager.htm).\
Add an AttributeManager transformer to the canvas and then connect it to the Passed output port of the SpatialFilter. Open the parameters. You can see all of the attributes that the LocalAddresses started with when we viewed the dataset in a [previous article](https://community.safe.com/s/article/getting-started-with-fme-desktop-view-data). There is also an additional parameter called *_predicate*, which was created in the SpatialFilter. We don't need _predicate, so we can remove it. Click on the line with **_predicate**, then click the negative **( - )** button at the bottom.\
![RemoveRow.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b3v)

After removing _predicate, you'll notice that the Input Attribute is still there, but the Output Attribute is blank; this is so you can reinstate it if you accidentally remove the wrong attribute or change your mind. If you were to change your mind, you could click on the drop-down box under **Action** and change it from **Removed** to **Do Nothing**.

![Remove.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b45)

While we're here, let's also rename the LOCALITY attribute to CITY. Click on the **LOCALITY** box under *Output Attribute*, and then type `CITY`. You'll notice that the *Action* has changed to *Rename*. Click **OK** to close the AttributeManager.\
![RenameCity.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7X&feoid=00N30000006n8wU&refid=0EM4Q0000028b4A)

#### 5. Click "Next"
