# Building Your First Pipeline in Azure Data Factory

Let’s walk through the steps to create a simple data pipeline.

## Step 1: Create linked services

### 1. Navigate to the Manage tab

Open your Azure Data Factory instance, and go to the Manage tab in the ADF interface. This is where you define linked services, which connect your data sources and destinations.

### 2. Add a linked service for the data source

Click on Linked services under the Manage tab.
Select + New to create a new linked service.
From the list of available options, select the data source you want to connect to, such as Azure Blob Storage.
Provide the required connection details, such as the storage account name and authentication method (e.g., account key or managed identity).
Test the connection to ensure everything is set up correctly, and click Create.

### 3. Add a linked service for the data destination

Repeat the process for the data destination, such as Azure SQL Database.
Select the appropriate destination type, configure the connection settings (e.g., server name, database name, and authentication method), and test the connection.
Once verified, save the linked service.

## Step 2: Create a dataset
### 1. Navigate to the Author tab

Open the Author tab in your Azure Data Factory interface. This is where you design and manage your pipelines, datasets, and other workflow components.

### 2. Add a dataset for the source

Click on the + button and select Dataset from the dropdown menu.
Choose the data store type that matches your source linked service. For example, if your source is Azure Blob Storage, select the corresponding data store type, such as Delimited Text, Parquet, or another relevant option.
Configure the dataset:

**Linked service:** Select the linked service you created earlier for the data source.

**File path:** Specify the path or container where your source data resides.

**Schema and format:** Define the data format (e.g., CSV, JSON) and import the schema if applicable. This allows ADF to understand the structure of your data.

Click OK to save the dataset.

### 3. Add a dataset for the destination

Repeat the process for the destination dataset.
Choose the data store type that matches your destination linked service. For example, if your destination is Azure SQL Database, select the appropriate type, such as Table.
Configure the dataset:

**Linked service:** Select the linked service you created for the destination.

**Table name or path:** Specify the table or destination path where the data will be written.

**Schema:** Optionally define or import the schema for the destination dataset to ensure compatibility with the source data.

Save the dataset.

# Step 3: Add activities
### 1. Open the Pipeline editor

In the Author tab, create a new pipeline by clicking + and selecting Pipeline.
This will open the pipeline editor, a visual interface where you can design your data workflows.

### 2. Add the copy data activity

From the toolbox on the left, locate the Copy data activity under the Move & Transform category.
Drag the Copy data activity onto the canvas. This activity moves data from the source to the destination.

### 3. Configure the copy data activity

Click on the Copy data activity to open its settings pane.
Under the Source tab:
    Select the source dataset you created earlier.
    Configure additional options such as file or folder filters if needed.
Under the Sink tab:
    Select the destination dataset.
Specify any additional settings, such as how to handle existing data in the destination (e.g., overwrite or append).
Use the Mapping tab to align the fields or columns from the source to the destination, ensuring data compatibility.
Save your configuration.

# Step 4: Publish and run the pipeline
### 1. Publish your pipeline

Once your pipeline is configured, click Publish in the toolbar.
This saves your pipeline and makes it ready for execution. Without publishing, changes made to your pipeline remain as drafts and cannot be run.

### 2. Run the pipeline

To test your pipeline, click Add Trigger at the top and select Trigger Now for a manual run. This allows you to verify that the pipeline is functioning as expected.
Alternatively, set up an automated schedule:
Go to the Triggers tab and create a new trigger.
Define the trigger conditions, such as a time-based schedule (e.g., every day at 8:00 AM) or an event-based condition (e.g., file arrival in Azure Blob Storage).
Associate the trigger with your pipeline to enable automation.
