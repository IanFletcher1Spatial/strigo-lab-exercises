1. Perform Spatial Analysis (Spatial Join)

Connect the road-ahead-upcoming-projects feature type output port to the Bufferer input port in the "Determine Impacted Area" bookmark by clicking and dragging between the ports.

Double-click the Bufferer to see how it is configured. It will create an area of 30 feet from the road center line (60 feet total width) around all upcoming road construction projects. We can use this area to identify food vendor locations that will be affected.

Run the workspace and inspect the Bufferer's Buffered port. If you zoom in, you will see the lines have been buffered into polygons.

Next, we need to find which food vendor points intersect (or overlay) the affected construction zones. We can use the SpatialFilter transformer for this job. Connect the Bufferer's Buffered port to the SpatialFilter Filter port.

Then delete the connection between the AttributeValidator and the writer feature type by right-clicking it and choosing Delete.

Next, connect the AttributeValidator's Passed port to the SpatialFilter's Candidate port. This step tells the transformer that the construction zones are the areas to filter on, and the vendor locations are the candidates to filter.

If you double-click the SpatialFilter, you will see it is configured to find intersecting features ("Filter OGC-Intersects Candidate"). Click Cancel.

Run the workspace. The feature counts for the SpatialFilter show that six food vendors will be affected by the road construction.

2. Perform an Attribute-Based Filter

The next step we want to accomplish is to enrich our spatial data with tabular data from another source. In this case, we'll be looking for business licenses matching the food vendor data. The other CSV feature type has the business license data, containing 572,634 rows. We want to join this data with the results of the SpatialFilter. Before joining, we should make sure we are only using current business licenses.

We can do this using the Tester transformer, which lets us conduct simple pass/fail logical tests on features to filter them. Connect the the Business Licenses CSV feature type to the Tester in the "Get Current License Data" bookmark.

Double-click the Tester to view its parameters. It is configured to filter out features that have a value of 21 for their `FOLDERYEAR` attribute. This attribute means they are valid for the year 2021. Click Cancel.

Run the workspace. The feature counts for the Tester show that 62,496 licenses are valid for 2021 (the Passed port). We will use these features and leave the remaining features in the Failed port, filtering them out of our data.

3. Perform an Attribute-Based Join

Now that we have impacted food vendors and a list of current business licenses, we can join this data together to add business license data to the impacted vendors.

Find the FeatureJoiner in the "Join Data and Manage Attributes" bookmark. Connect the SpatialFilter's Passed port to the FeatureJoiner's Left port and the Tester's Passed port to the FeatureJoiner's Right port.

Double-click the FeatureJoiner to view its parameters. This transformer conducts an SQL-style join. It is setup to do an Inner join (keep only matching records), and to use the shared keys of `BUSINESS_NAME` AND `BusinessTradeName`. Click Cancel.

Run the workspace. Based on the feature counts for the FeatureJoiner, you should be able to see that two of the affected vendors had matching valid license data found, so they came out of the Joined port. Two did not have a valid license, so they came out of the UnjoinedLeft port. At first this might be worrying, but if you do look up the licenses for these businesses, you will see they are actually out of business, despite our source food vendor data claiming they are open. We do not need to alert an out-of-business food vendor, so it is OK that these two features will be filtered out of our data.

4. Manage Attributes

The final step before we write out our data to create an Excel file of business to alert is to clean up our Attributes. We will use an AttributeManager to rename and remove some attributes.

Find the AttributeManager on the right side of the "Join Data and Manage Attributes" bookmark, next to the FeatureJoiner. Connect the FeatureJoiner's Joined port to the AttributeManager input port.

Double-click the AttributeManager to view its parameters. This transformer lets you rename, remove, add, and change values for attributes. This already-configured transformer removes many unnecessary attributes and renames a few others. You can see how each attribute is being modified by looking at the Action column, which will say "Rename" or "Remove." Click Cancel.

Run the workspace. If you inspect the AttributeManager's feature cache, you will see how the attributes have changed.

5. Write the Data

The final step is to write the data to Excel. Connect the AttributeManager's Output port to the Excel writer feature type input port. Run the workspace to write out the data.

To confirm the data was written successfully you can refer to the Translation Log (the last line should report `Translation was SUCCESSFUL`). You can also find the output data by clicking the writer feature type once to select it, then clicking the Open Containing Folder button that appears in the small toolbar above to find the Excel file. You can open it in Excel or Open Office if you want to confirm it was written correctly.

6. Continue to Next Article

Click the Next button below.
