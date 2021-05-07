Introduction
------------

Once the data has been read into the workspace and manipulated with transformer(s) (if desired), it needs to be written out to a file using a writer. In part five of this tutorial series, you will learn how to add and set up a writer.

Scenario
--------

A water pump has failed and will require maintenance. In order for the pump to be replaced, the water utility company will have to shut off water for an entire service area. You have a list of customer addresses but are not sure which service area these customers belong to. Using a dataset of all the water service areas, you will overlay the addresses on the affected area to determine which customers belong to that area. Then after the customers have been determined, a Microsoft Excel spreadsheet will be created so someone can notify the customers.

Exercise
--------

Now that we have filtered out which customers are within the affected water_service_area, as well as cleaned up the attributes, we are now ready to write the data out to a Microsoft Excel spreadsheet.

#### Step-by-Step Instructions

Continue working in the workspace from the [previous article](https://community.safe.com/s/article/getting-started-with-fme-desktop-modify-attributes) or download the GettingStarted-AddAWriter-Begin.fmwt workspace.\
![StartingWorkspace.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bX7)

1\. Add a Writer\
Now that the points have been filtered to include only the ones that fall within the water_service_area boundary that has a RED status, and we've cleaned up the attributes, we can now write out the data.  The utility company has requested the list of addresses be in a Microsoft Excel spreadsheet.

To add a writer to the canvas, click on the Writer button on the top menu bar or by going to Writers > Add Writer.\
![WriterButton.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bXC)

2\. Introduction to the Add Writer Dialog\
A writer is a way to "write" data out of FME. Depending on the dataset you are planning on writing out, the parameters for the Add writer dialog may change. Let's go over the Add Writer dialog, which is similar to the Add Reader dialog, and set our parameters for the Microsoft Excel spreadsheet. 

![AddWriterDialog.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bXH)

*a. Formats and Dataset*\
In the Add Writer dialog, select the Format in which you want your output data to be. Next, choose a location to save the dataset, depending on the format you might also input a filename.\
Set the Format to Microsoft Excel and then browse to a location to save the file by clicking on the ellipsis next to Dataset. After selecting a location, input AddressesToNotify.xlsx as the filename.\
![ExcelLocation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bXM)

*b. Parameters*\
Each format has specific parameters that can be set. To check the parameters, click on the Parameters button, which will bring up the Format Parameters dialog. If the Parameters button has an exclamation point ( ! ) at the end of it, this means that there are mandatory parameters that need to be set. To learn more about the format's specific parameters you can click on the Help button in the Parameters window.\
We can accept the default parameters for the Microsoft Excel writer.

*c. Coordinate System*\
The writer will keep the coordinate system that was in the original dataset or set during the workspace. If you would like the output dataset to be in a different coordinate system, you can enter the desired coordinate system in the Coord. System box to reproject on the fly.\
We will leave it blank for this tutorial.

*d. Add Feature Type(s)*\
The Add Feature Type(s) section determines how the schema will be written out. To have the output attributes reflect what was done in the workspace, select Automatic. To manually select which attributes are written out, choose Manual. Finally, to use the same attributes as the original reader, select Copy From Reader. To learn more about adding feature types,  click on Help > Add Writer in the Add Writer dialog. Note that the terminology in this section will change based on the format.\
![Help.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bWP)

Select Automatic for the Sheet Definition; this will ensure that our writer automatically reflects the attribute changes that we did in the AttributeManager. Click OK to add the writer.\
![SheetDefinition.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bXR)

3\. Feature Type Dialog\
When you set the Definition to Automatic in the Add Writer dialog, the details about the Feature Type name will need to be defined. After clicking the OK button in the Add Writer dialog, a Feature Type dialog appears. In this dialog, you will need to set the Feature Type Name; this will be the name of the layer or worksheet.

Set the Sheet Name to Addresses and click OK. There are other parameters that could be set for the Microsoft Excel writer, but they can be left as default for this tutorial.\
![FeatureType.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bXb)

4\. Connect the Writer Feature Type\
Once the Addresses writer feature type has been added to the canvas, it needs to be connected to the workflow. Click on the output port of the AttributeManager transformer drag to connect to the writer feature type input port.\
![ConnectedWriter.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7m&feoid=00N30000006n8wU&refid=0EM4Q0000028bXl)

5\. Continue to Next Article\
If you are continuing to the [next article](https://community.safe.com/s/article/getting-started-with-fme-desktop-write-data), please leave your workspace open.
