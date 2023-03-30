# Setting Up APS Data Visualization in Power BI Desktop



These are the steps to follow to set up Microsoft Power BI Desktop to use the APS Data Visualization data connector and visual.

**Pre-requisites**

To complete this installation, you need the following:

- A Windows computer, or Windows virtual machine, to run Power BI Desktop
- Power BI Desktop (see [Get Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/fundamentals/desktop-get-the-desktop) to download)
- A Power BI account on app.powerbi.com, for publishing reports using Power BI (web)
- An APS account or BIM 360 account – If you do not have an APS account, go to [Autodesk Account](https://learnAPS.autodesk.io/#/account/)
- A model and access to the data (typically a Revit file)

[Installing and configuring the data connector](https://aps.autodesk.com/en/docs/endymion/v1/developers_guide/setup/#installing-and-configuring-the-data-connector)

### Enabling data extensions in Power BI Desktop

To avoid warning messages when you load the APS viewer extensions, do the following:

1. In Windows, make sure that the following folder exists: **This PC > Documents > Microsoft Power BI Desktop > Custom Connectors**.
2. In Power BI Desktop, go to **File > Options and settings > Options > Security > Data Extensions**, and choose the **(Not Recommended) Allow any extension to load without validation or warning** option.

> [![Options Security](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-options-security.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-options-security.png)

1. Click **OK**.
2. Close Power BI Desktop. (Ordinarily you would restart it, but the next step also requires restarting.)

### Downloading and installing the data connector

1. Download the data connector: https://hyperion-dev-assets.autodesk.io/mez/latest/DataVizPowerBIConnector.mez
2. Install the *.mez* file in **This PC > Documents > Microsoft Power BI Desktop > Custom Connectors**. (You may have to create this folder if it doesn’t exist yet.)
3. Launch (or restart) Power BI Desktop.

### Launching the data connector

1. In Power BI Desktop, go to **Home > Add data to your report > Get data from another source**.
2. In the **Get Data** window, find *DataVizPowerBIConnector (Beta)**.

> [![Get Data](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-get-data.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-get-data.png)

1. Click **Connect**.
2. The first time you connect, you will need to sign in using your Autodesk APS or BIM 360 login email address. This authorizes the Power BI Desktop application to work with the data.

When connected, this takes you to the Navigator for the projects you can access from your account.

### Importing a model (typically a BIM 360 file)

1. In **Navigator > Display Options**, find the project you want to display, and open up the **Project Files**. The DataViz Connector displays the same folder hierarchy that you are used to seeing in BIM 360, except that it filters out any files — like image or text files — that are not displayable in the Viewer. Each displayable model file is represented by a folder containing the available viewables for that model.
2. Open the folder representing model you want to import. Some viewables (such as a PDF or DWF rendering of the model) will have a single view. A Revit (*.rvt*) model can have multiple 2D or 3D viewables.

> [![Navigator Models](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-navigator-models.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-navigator-models.png)

1. Open the folder representing one of the viewables. Every 2D or 3D viewable will have two loadable tables: a **Config** table and a **Model Properties** table.)

> [![Config Model Properties](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-config-model-properties.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-config-model-properties.png)

1. Select the **Config** table, and (if provided) the **Model Properties** table to enable them for loading.
2. (Optional) If you have additional models, and want to load them at the same time, repeat steps 2—4 for each of them.
3. Click **Load**. Loading can take a few moments, especially if you are loading multiple models with large data tables.

*The return window says “Build visuals with your data: Select or drag fields from the Fields pane onto the report canvas.”*

[Installing and importing the APS visual](https://aps.autodesk.com/en/docs/endymion/v1/developers_guide/setup/#installing-and-importing-the-APS-visual)

### Installing the visual

To install the APS Visual in Power BI Desktop:

1. In a browser, download the visualization, https://hyperion-dev-assets.autodesk.io/pbiviz/latest/viewerCard.pbiviz
2. In Power BI Desktop, go to **Visualizations > Import a visual from a file**.

> [![Import Visual From A File](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-import-a-visual-from-a-file.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-import-a-visual-from-a-file.png)

1. Find and select *viewerCard.pviz*.
2. This adds an icon, (tooltip: *ViewerCard*) to the **Visualizations** pane.

> [![ViewCard Icon](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-viewcard-icon.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-viewcard-icon.png)

To sign in and configure the APS Viewer Visual: 1. Click the *ViewerCard* visual in the **Visualizations** pane to open it. 2. Follow the instructions to sign in, and configure the visual.

The following sections explain the displayed instructions a little further.

### Getting the temporary access token for Autodesk APS

1. Click the *ViewerCard* visual in the **Visualizations** pane to open it.

> [![Configure ViewCard Blank](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/configure-viewcard-blank.png)](https://aps.autodesk.com/en/docs/endymion/_images/configure-viewcard-blank.png)

1. To sign in to APS, click the *Autodesk APS* link in the configuration window.
2. When this opens your browser, sign in using your email and password. This displays a window with your temporary access token.

> [![Copy Token](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/copy-token.png)](https://aps.autodesk.com/en/docs/endymion/_images/copy-token.png)

1. Click **Copy the Token** to copy it to your clipboard.
2. Back in Power BI Desktop, paste your token in the provided box.

> [![Configure ViewCard Token](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/configure-viewcard-token.png)](https://aps.autodesk.com/en/docs/endymion/_images/configure-viewcard-token.png)

### Configuring the visual

1. In the **Fields** pane, open the **Config** table for the model and drag the **urn** field into the **Config** section of the APS Viewer Visual, to bind the URN for the field.
2. (Optional) Drag any of the other **Config** fields (like **guid** or **region**) into the APS Viewer Visual Config box.
3. Open the **Model Properties** table for the model, and drag the **externalID** field into the **Model Properties** section of the APS Viewer Visual.

> [![Configure The Visual](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-configure-visual.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-configure-visual.png)

The **externalID** is what lets you select sections of the model to display in the visualizations.

[Testing the installation](https://aps.autodesk.com/en/docs/endymion/v1/developers_guide/setup/#testing-the-installation)

To verify that everything is installed and configured properly, here are a few tests to run.

### Turning ‘Zoom to selection’ and ‘Ghost on selection’ on or off

The APS Visual Config settings let you control the zooming and ghosting whenever you select objects in the visual.

1. If not already displayed, click the *ViewerCard* visual in the **Visualizations** pane to open it.
2. Select the second tab (the paint roller symbol) to display the Format pane.
3. Click **APS Viewer Configuration** to display the configuration options.

> [![Configure ViewCard Zoom Ghost](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/configure-viewcard-zoom-ghost.png)](https://aps.autodesk.com/en/docs/endymion/_images/configure-viewcard-zoom-ghost.png)

1. Click the **Zoom to selection** or **Ghost on Selection** to turn these settings on or off.

### Selecting parts of the model

To test that everything is configured properly, try selecting parts of the model using another visual:

1. Select the table visual to add it to the model window. When empty, this table reads **Select or drag fields to populate this visual.**

> [![Select Table Viz](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-select-table-viz.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-select-table-viz.png)

1. Drag **externalID** and **name** into the **Values** pane.

> [![Add ExternalID And Name To Values](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-add-externalid-name-to-values.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-add-externalid-name-to-values.png)

1. To select the various parts of the model, click any of the rows in the table.

> [![Select Parts Of The Model](https://developer.doc.autodesk.com/bPlouYTd/A360-endymion-docs-master-30814/_images/pbi-select-parts-of-the-model.png)](https://aps.autodesk.com/en/docs/endymion/_images/pbi-select-parts-of-the-model.png)

Note that it is not necessary to have dragged the **name** property into the APS View Visual Model Properties. As long as you have dragged the **externalID**, this is enough to match the selected row of the table in the two visuals.

[Publishing and Sharing Reports in Power BI](https://aps.autodesk.com/en/docs/endymion/v1/developers_guide/setup/#publishing-and-sharing-reports-in-power-bi)

Once you have configured the visuals to create your report, you can save it, publish it, and share it with others.

### Publishing the report

To publish the report:

1. If you haven’t already created a Power BI workspace, use your browser to go to your Power BI space on [https://app.powerbi.com](https://app.powerbi.com/), go to **Home > Workspaces** and click **Create a workspace**.
2. In Power BI Desktop, display your configured report, click the **Save** button, and give your report a name.
3. Click the **Publish** button to display the **Publish to Power BI** window.
4. Choose the target workspace, and click **Select**. Use **My workspace**, which is only viewable by you, for testing.
5. When publishing is done — which can take a few minutes — click on the provided link to open the report in Power BI.

### Sharing the report

To share the report in Power BI (Web):

1. In Power BI (Web), make sure you are displaying the report, and that you are not editing it. (You cannot share the report while in Edit mode.)
2. Click the **Share** button.
3. You can choose to share to a name or email address, or click Copy Link to copy a link to the report in your Clipboard for pasting in other applications.

For more information about sharing Power BI reports, see https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-share-dashboards.

### Updating the data in the report

Although you can can interact with, and edit, the report itself directly in Power BI, the loaded data is static — it contains the data in effect at last publication. If you want to update the data bound to the report, you need to do this in Power BI Desktop, and then re-publish.

1. In Power BI Desktop, open your report if not displayed already.
2. Click the **Refresh** button to refresh the data.
3. Click the **Publish** button to re-publish the data to the target workspace.

[Links to further information](https://aps.autodesk.com/en/docs/endymion/v1/developers_guide/setup/#links-to-further-information)

Microsoft offers a number of different sources for documentation on Power BI and Power BI Desktop.

- Main Power BI documentation hub:  [Power BI documentation](https://docs.microsoft.com/en-us/power-bi/)
- Downloading and installing Power BI Desktop: [Get Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/fundamentals/desktop-get-the-desktop)
- Getting started: [Power BI get started documentation](https://docs.microsoft.com/en-us/power-bi/fundamentals/)
- Working with data: [Connect to data in Power BI](https://docs.microsoft.com/en-us/power-bi/connect-data/)
- Creating and sharing reports: [Create reports and dashboards in Power BI](https://docs.microsoft.com/en-us/power-bi/create-reports/)