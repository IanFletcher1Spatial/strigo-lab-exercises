**Step 1**

Find the Bufferer transformer in the "Determine Impacted Area" bookmark.

IMAGE

**Step 2**

The Bufferer is configured to create features representing the areas within 30 feet of the road centerline, i.e., areas impacted by construction.

Inspect the Bufferer's Buffered port feature cache. If you zoom in, you will see the lines have been buffered into polygons.

IMAGE

**Step 4**

Find the SpatialFilter transformer in the "Find Impacts" bookmark.

IMAGE

**Step 5**

The SpatialFilter is configured to find food vendors within the buffered areas.

Observe the feature counts for the SpatialFilter's Passed port. Four food vendors will be affected by the road construction.

IMAGE

**Step 6**

Find the Tester.

images

**Step 7**

The Tester is configured to filter out business licenses that are not valid for the year 2021.

Observe the Tester's feature counts. 62,496 licenses are valid for 2021 (the Passed port). We will use these features and leave the remaining features in the Failed port, filtering them out of our data.

**Step 8**

Now that we have impacted food vendors and a list of current business licenses, we can join this data together to add business license data to the impacted vendors.

Find the FeatureJoiner in the "Join Data and Manage Attributes" bookmark. Note that the SpatialFilter's Passed port is connected to the FeatureJoiner's Left port and the Tester's Passed port is connected to the FeatureJoiner's Right port.

Double-click the FeatureJoiner to view its parameters. This transformer conducts an SQL-style join. It is setup to do an Inner join (keep only matching records), and to use the shared keys of `BUSINESS_NAME` AND `BusinessTradeName`. Click Cancel.

Based on the feature counts for the FeatureJoiner, you should be able to see that two of the affected vendors had matching valid license data found, so they came out of the Joined port. Two did not have a valid license, so they came out of the UnjoinedLeft port. At first this might be worrying, but if you do look up the licenses for these businesses, you will see they are actually out of business, despite our source food vendor data claiming they are open. We do not need to alert an out-of-business food vendor, so it is OK that these two features will be filtered out of our data.

4. Manage Attributes

The final step before we write out our data to create an Excel file of business to alert is to clean up our Attributes. We will use an AttributeManager to rename and remove some attributes.

Find the AttributeManager on the right side of the "Join Data and Manage Attributes" bookmark, next to the FeatureJoiner. Note that the FeatureJoiner's Joined port is connected to the AttributeManager input port.

Double-click the AttributeManager to view its parameters. This transformer lets you rename, remove, add, and change values for attributes. This already-configured transformer removes many unnecessary attributes and renames a few others. You can see how each attribute is being modified by looking at the Action column, which will say "Rename" or "Remove." Click Cancel.

If you compare the FeatureJoiner's Joined port cache to the AttributeManager's Output port cache, you will see how the attributes have changed.

5. Clean Up Connection Lines

Delete the connection between the AttributeValidator and the writer feature type by right-clicking it and choosing Delete.

Add a new connection line between the AttributeManager's Output port and the AffectedVendors writer feature type by clicking and dragging from the right-pointing gray triangle on the Output port to the right-pointing gray triangle on AffectedVendors. Let go to make the connection.

5. Write the Data

The final step is to write the data to Excel. Run the workspace to write the data.

To confirm the data was written successfully you can refer to the Translation Log (the last line should report `Translation was SUCCESSFUL`). You can also find the output data by clicking the writer feature type once to select it, then clicking the Open Containing Folder button that appears in the small toolbar above to find the Excel file. You can open it in Open Office if you want to confirm it was written correctly.

6. Continue to Next Exercise

Click the Next button below.
