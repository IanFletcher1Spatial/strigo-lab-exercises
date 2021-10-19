1. Connect AttributeValidator

Find the AttributeValidator in the "Validate Food Truck Data" bookmark to the right of the reader feature types. Click and drag to move it. Note a green right-pointing arrow appears in the top left corner of the transformer as you drag it. Move your mouse so that triangle intersects the connection line between your feature types. When it does, the line will highlight green. When this happens, release your mouse to connect the transformer between your feature types. Now it will run, using the food vendor data provided along the connection line.

2. View AttributeValidator Parameters

Double-click the AttributeValidator to view its parameters in a dialog.

Like the rest of the transformers in this workspace, it is already configured. This transformer tests features to ensure each has a unique value for `KEY` and has a value for `BUSINESS_NAME`. Click OK without making any changes.

3. Run Workspace

Hover over the Run button. You will notice that only parts of the workspace are highlighted in green. These parts will run. The rest will use feature caches and will not be rerun. This "partial runs" technique saves time when authoring your workspace. The workspace does not re-read the data from the CSV, but uses the cache instead.

Run the workspace.

4. Observe Streams in Data

After the workspace runs, you should notice that the feature counts show how the data has been split into two streams by the AttributeValidator. 16 features come out of the Failed port (they did not meet the validation rules), while 75 come out of the Passed port and continue on to be written.

Splitting data by transformer ports is a common way that different streams of data are created in FME. Using multiple streams lets you ensure your data is going to the correct place. If you wanted to do something with these 16 features, like add an attribute `VALIDATION` = "Failed" or email them to a colleague responsible for fixing them, you could do so here.

5. Continue to Next Article

Click the Next button below.
