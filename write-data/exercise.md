1. Examine the Excel Writer

The "Create a Report in Excel" bookmark (on the bottom-right of the Canvas) contains a writer feature type called AffectedVendors. Let's figure out where it will write data. Click it once to select it. When you select it, its writer in the Navigator window will also be highlighted in gray: AffectedVendors [XLSXW]. Click the right-pointing arrow next to the writer in the Navigator to expand its parameters. The Destination Microsoft Excel File parameter tells us this writer will create data at C:\\FMEData2021\\Output\\Training\\AffectedVendors.xlsx.

2. Connect Reader and Writer Feature Types

Click the right-pointing arrow (output port) on your food vendors CSV reader feature type and drag the connection line to the red right-pointing arrow on your Excel writer feature type. Let go to connect the objects.

Note: because we already have transformers in our workspace, but they are not connected, the connection lines will get a bit confusing here, passing behind the AttributeValidator, for example. That's OK for now; we'll clean it up soon.

Because the writer feature type was created using Automatic Sheet Definition mode, the writer feature type uses the schema of connected features. You should see the new attributes appear below the writer feature type.

3. Run the Workspace

Click the Run button to run the workspace and convert your CSV to Excel. If the Translation Parameter Values dialog appears, just click Run.

4. View the Written Data

After "Translation was SUCCESSFUL" appears as the last line in your Translation Log, the workspace has finished running.

To confirm the Excel file was written, click the writer feature type once to select it. Then click the Open Containing folder icon that appears on the small toolbar above the feature type. This button lets you open the folder where data was written in Windows Explorer. You should see a new AffectedVendors.xlsx file. To inspect the written data, you can open it with Microsoft Excel.

5. Continue to Next Article

Click the Next button below.
