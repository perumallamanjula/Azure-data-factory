## Core Components of Azure Data Factory

## 1. Pipelines
Pipelines are the backbone of Azure Data Factory. Logical groupings of activities that perform a unit of work.
Activities within a pipeline can be chained together to operate sequentially or in parallel.
They represent data-driven workflows that define the steps required to move and transform data.

## 2. Activities
Activities are the functional building blocks of pipelines, each performing a specific operation.

They are broadly categorized into:

### 1.Data movement activities
These activities facilitate data transfer between different storage systems. For example, the "Copy data" activity moves data from Azure Blob Storage to an Azure SQL Database.

### 2.Data transformation activities
These activities allow you to manipulate or process data. For instance, data flows or custom scripts can be used to transform data formats, aggregate values, or cleanse datasets.

### 3.Control flow activities
These manage the logical flow of execution within pipelines. Examples include conditional branching, loops, and parallel execution, which provide flexibility in handling complex workflows.

## 3. Datasets
Datasets are representations of the data utilized in activities. They define the schema, format, and location of the data being ingested or processed.
Represent data structures within data stores, used as inputs or outputs for activities 

## 4. Linked services
Linked services are connection strings that enable activities and datasets to access external systems and services. 
They act as bridges between Azure Data Factory and the external resources it interacts with, such as databases, storage accounts, or compute environments. 

## 5. Integration runtimes
Integration runtimes (IRs) are the compute environments that power data movement, transformation, and activity execution within Azure Data Factory. ADF provides three types of integration runtimes:

Azure IR: Handles cloud-based data integration tasks and is managed entirely by Azure.
Self-hosted IR: Supports data movement between on-premises systems and the cloud, making it ideal for hybrid scenarios.
SSIS IR: Enables the execution of SQL Server Integration Services (SSIS) packages within Azure, allowing you to reuse existing SSIS workflows in the cloud.
