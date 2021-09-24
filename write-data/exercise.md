1. Add an Excel Writer

Click on an empty space on the Canvas. Type Excel. Choose "Microsoft Excel" from the list of Writers (make sure you don't choose a Reader!). Double-click it to add an Excel writer.

Configure the Add Writer dialog as follows:

| Parameter                            | Value                                                   |
|--------------------------------------|---------------------------------------------------------|
| Format                               | Microsoft Excel                                         |
| Dataset                              | C:\\FMEData2021\\Output\\Training\\AffectedVendors.xlsx |
| Coord. System                        | LL84                                                    |
| Sheet Definition                     | Automatic                                               |
| Parameters > Overwrite Existing File | Yes                                                     |

Click OK.

When the Feature Type dialog appears, set the Sheet Name to AffectedVendors. Click OK. The writer feature type will appear on the Canvas. Move the feature type to the "Create a Report in Excel" bookmark.

2. Connect Reader and Writer Feature Types

Click the right-pointing arrow (output port) on your food vendors CSV reader feature type and drag the connection line to the red right-pointing arrow on your Excel writer feature type. Let go to connect the objects.

Because we used Automatic Sheet Definition mode, the writer feature type uses the schema of connected features. You should see the new attributes appear below the writer feature type.

3. Run the Workspace

Click the Run button to run the workspace and convert your CSV to Excel. If the Translation Parameter Values dialog appears, just click Run.

4. View the Written Data

To confirm the Excel file was written, click the writer feature type once to select it. Then click the Open Containing folder icon that appears on the small toolbar above the feature type. This button lets you open the folder where data was written in Windows Explorer. You should see a new AffectedVendors.xlsx file.

NOTE: CAN'T VIEW IN VP, COORD SYSTEM WRONG... Not sure why.

5. Continue to Next Article

Click the Next button below.
