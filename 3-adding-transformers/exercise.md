<head><base target="_blank"> </head>
------------

Data transformation is FME's ability to manipulate data. The transformation step occurs during the process of format translation. Data is read, transformed, and then written to the chosen format. A transformer is an FME Workbench object that carries out the transformation of features. Each transformer has its own unique function and can be strung together in a series to achieve complex tasks. In part three of this tutorial series, we will add a transformer to the canvas using Quick Add and then modify the parameters.

Scenario
--------

A water pump has failed and will require maintenance. In order for the pump to be replaced, the water utility company will have to shut off water for an entire service area. You have a list of customer addresses but are not sure which service area these customers belong to. Using a dataset of all the water service areas, you will overlay the addresses on the affected area to determine which customers belong to that area. Then after the customers have been determined, a Microsoft Excel spreadsheet will be created so someone can notify the customers.

Exercise
--------

When we viewed the data in Visual Preview, we noted that we can select only the water_service_area that has the Status of RED. To select this water_service_area, we will use the Tester transformer.

#### Step-by-Step Instructions

Continue working in the workspace from the [previous article](https://community.safe.com/s/article/getting-started-with-fme-desktop-view-data) or download the GettingStarted-AddingTransformers-Begin.fmwt workspace.

1\. Add a Transformer\
When modifying data in FME, you will need to use a transformer. To add a transformer, click anywhere on the canvas and start typing the transformer name you wish to add. When you start typing, the Quick Add dialog will appear; from this dialog transformers, readers, and writers can be added by just typing their name.\
![QuickAddTester.gif](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b1u)

Once you have found the transformer you are looking for in Quick Add, either click Enter on the keyboard or double-click it with the mouse to add it to the canvas.\
![TesterQuickAdd.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b1z)

To start, we will add a Tester transformer. This transformer will let us filter the data based on an attribute value, such as STATUS = RED.

2\. Connect the Transformer\
To use the transformer, it must be connected to the workflow. Click on the output arrow on the water_service_area reader feature type and drag to the input arrow on the Tester transformer. When they are correctly connected, a line will appear between them. Additionally, once they are connected attributes from earlier in the workflow can be accessed in the transformer.\
![ConnectionLine.gif](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b24)\
3\. Open the Transformer Parameters\
The parameter button (cogwheel) on a transformer is color-coded to reflect the status of the settings.\
A red cogwheel indicates that there is at least one parameter value that needs to be added.\
![ParamRed.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b25)\
A yellow cogwheel indicates the default parameters have been automatically chosen but should be confirmed.\
![ParamYellow.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b29)\
A cogwheel that matches the transformer color indicates that the parameters were checked or set and the transformer is ready to use.\
![ParamBlue.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b2E)\
To open the transformer parameters dialog, double-click on the transformer. Parameters for each transformer are different. To learn about parameters specific to the transformer, click on the Help button to open the documentation.\
![Help.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b2J)

Double-click on the Tester transformer to open the parameters.

4\. Create a Test in the Tester\
In the Tester parameters, a test clause (conditional statement) can be created to filter data. Click on the red box under Left Value to show the drop-down arrow. Click on the drop-down arrow and expand Attribute Value, then click on STATUS.\
![TesterRightValue.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b2T)\
This drop-down menu shows all of the attribute values available for a specific parameter.\
Next, click on the box under Right Value and type in RED. Automatically the Operator gets set to equals by default. If you are looking for a different operator, click on the box to expand the list. Click OK to accept the parameters and close the dialog. For more information on using the Tester, see the [documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Transformers/Transformers/tester.htm).

Note: As of 2020.1 or newer, certain transformers are data-aware, which enables the user to select cached values from within the transformer instead of manually typing them. For this tutorial, we will be manually typing in the values. For more information, see this [Expert Note](https://community.safe.com/s/question/0D54Q00008C1GaNSAV/expert-notes-dataaware-transformers-in-20201).\
![SetUpTester.gif](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b2n)

5\. Run and Inspect the Test\
Since feature caching is enabled, the workspace can be run to the Tester, and the caches can be inspected in Visual Preview. Running your workspace often to check that the output is what you expected from a transformer is good practice.\
Click on the Run button on the top menu bar. After the workspace has run, there should be a 1 next to the Passed output port on the Tester, and a 3 next to the Failed output port. Click on the green magnifying glass on the Passed output port to open it in Visual Preview.\
![RunTester.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b2s)

In Visual Preview, you can confirm that there is one water_service_area with the Status of RED.\
![TesterOutput.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7S&feoid=00N30000006n8wU&refid=0EM4Q0000028b2x)

6\. Continue to Next Article\
If you are continuing to the [next article](https://community.safe.com/s/article/getting-started-with-fme-desktop-modify-attributes), please leave your workspace open.
