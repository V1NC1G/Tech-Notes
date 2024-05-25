Tags: [[Database]]
# Data Warehouse

> [!summary] 
> A **data warehouse** is like a [[Data Lake|data lake]] except that the information found there has been processed and cleaned so it is easily acceptable.

To achieve this, data from the lake is extracted, formatted, validated, summarized, and otherwise processed and stored in a data warehouse where it is possible to get actionable intelligence from the data.

![[data-warehouse-data-processing.excalidraw|100%|center]]

## Benefits

- Acts as a single source of truth where past performances can be compared to the current performance.
	- For example, if a company implements a new format for keeping logs, it can reference the store of historical logs to prove the effectiveness of the approach.
- Allows data filtering and cleaning, and facilitates analysis to get essential and actionable information.
- Stores data in a structured way making it easy to apply learning models to data without first having to change how the data is presented.
- Leads to greater awareness of data and enables better vetting process for appropriate access.

## Challenges

- Takes a significant effort to create a data warehouse from a data lake due to the challenge of knowing how the data is structured without deep investigation.
- Domain expertise is needed to orchestrate data because of the potential cost of transferring and processing data from data lakes.
- Challenging to clean data into a desirable format with the amount of data items.

## [[Azure]] Data Warehouse Technologies

- [[Azure SQL Database]]: fully managed relational cloud database that provides automatic patching, inbuilt security, and data protection on demand.
- [[Azure Synapse Analytics]]: service that optimizes analytics tasks to deliver faster insights. It provides integration between Microsoft's data warehousing and big data analytics capabilities in one service.
- [[Apache Hive]]: a data warehouse built on top of [[Hadoop]] for providing data summarization, query, and analysis.

---
# References

1. Microsoft Cybersecurity Analyst Professional Certificate

___
## Flashcards

Flashcard Tags: #database 

A type of storage like a data lake except that the information found there has been processed and cleaned so it is easily acceptable.
?
Data Warehouse
