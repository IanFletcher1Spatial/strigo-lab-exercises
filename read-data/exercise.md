**Step 1:**

You should see an FME Workbench window with the workspace `C:\\FMEData2021\\Resources\\FMEAccelerator\\FoodVendors-Start.fmw` loaded.

**Step 2:**

Explore the workspace.

Three existing reader feature types (data sources) are on the left: upcoming road construction projects and business licenses are labelled. A third unlabeled CSV reader feature type is on the canvas.

![Reader feature types](./images/reader-feature-types.png)

The bookmarks (containers) and annotation (comments) containing comments about what step will take place where. The blue objects in the middle of the workspace are the transformers we will use to build our workspace. They are already configured and connected for the sake of speed.

**Step 3:**

Click the "CSV" reader feature type without annotation once to select it. It will be highlighted in blue to show it is selected.

![Selecting a reader feature type](./images/select.png)

_Explanation:_

We can see one of these reader feature types is not annotated, so we don't know which dataset it corresponds to. We can select it to figure out what data it is reading.

**Step 4:**

When you selected the reader feature type, its reader in the Navigator window (top-left) will also be highlighted in gray: food-vendors [CSV2]. Find this item in the Navigator.

![Seeing a reader highlighted in the Navigator](./images/navigator.png)

_Explanation:_

Reader feature types are displayed on the canvas and each belongs to a single reader. Readers are displayed in the Navigator. Selecting a reader feature type highlights the reader it belongs to.

**Step 5:**

Click the right-pointing arrow next to the reader in the Navigator to expand its parameters.

![Expanding a reader in the Navigator](./images/arrow.png)

Hover over the Source CSV (Comma Separated Value) File(s) parameter, the first in the expanded list. A tooltip appears telling us this CSV reader is using data located at `C:\\FMEData2021\\Resources\\FMEAccelerator\\data\\food-vendors.csv`.

![Viewing the source path for a reader](./images/source.png)

_Explanation:_

**Step 6:**

Click the Next button below.
