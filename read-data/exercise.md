1. Open Workspace

Open the workspace by double-clicking the file located at C:\\FMEData2021\\Resources\\FMEAccelerator\\FoodVendors-Start.fmw.

2. Examine Workspace

Note two existing reader feature types (data sources) on the left: upcoming road construction projects and business licenses. Note the bookmarks containing comments about what step will take place where. Note the Transformers bookmark at the top, which contains the "building blocks" we will use to build our workspace. They are already configured for the sake of speed.

3. Add a CSV Reader

We need to read the food vendor data from a CSV file. Click on a blank space on the Canvas and type CSV. The Quick Add dialog will pop open. Select "CSV (Comma Separated Value)" under the Readers section. Double-click it to add a CSV reader.

Configure the Add Reader dialog as follows:

| Parameter                         | Value                                                                                                                                     |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| Format                            | CSV (Comma Separated Value)                                                                                                               |
| Dataset                           | C:\\FMEData2021\\Resources\\FMEAccelerator\\data\\food-vendors.csv                                                                             |
| Coord. System                     | LL84                                                                                                                                      |
| Parameters > Delimiter Character  | ,                                                                                                                                         |
| Parameters > Attributes > x and y | Type should be x_coordinate and y_coordinate, respectively. If they are not, change Attribute Definition to Manual and set them manually. |
|                                   |                                                                                                                                           |

After configuring the dialog, click OK.

You will see a new Reader appear in the Navigator ("food-vendors [CSV2]") and a new reader feature type "CSV" appear on the Canvas. Drag the feature type over between the other two reader feature types.

4. Save Your Workspace

Click the Save button on the Toolbar.

5. Continue to Next Article

Click the Next button below.
