# Relational and Vector Databases

In this lab, you will explore two ways to organize and retrieve data. Use **SQL Playground** to build a relational database from original research, query it, and visualize your findings. Then use **RAG Playground** to experiment with indexing, chunking, and retrieving text, images, and audio across at least two projects. Submit your database, visualizations, written insights, project exports, and node graph screenshots in one Box folder, and share its link on Canvas.

## 1. Relational Databases

### What are Relational Databases?

Relational databases store data in **tables** made up of **rows** and **columns**, with clearly defined relationships between tables. They are designed to keep data structured, consistent, and easy to query.

Key concepts include:

* **Tables** – collections of related data.
* **Rows** – individual records in a table.
* **Columns** – named fields that define the data type of each value.
* **Primary keys** – unique identifiers for rows.
* **Foreign keys** – references that link data across tables.
* **Schemas** – logical groupings that organize database objects.

Relational databases like **PostgreSQL**, **MySQL**, and **SQLite** are widely used because they keep data accurate, consistent, and reliable.

### Common Types of Relationships

Relational databases model how data connects across tables using relationships. The three most common types are:

* **One-to-One (1:1)** – A single row in one table relates to a single row in another table.
  *Example: a user and a user profile.*

* **One-to-Many (1:N)** – One row in a table relates to many rows in another table. This is the most common relationship type.
  *Example: a customer placing many orders.*

* **Many-to-Many (N:M)** – Many rows in one table relate to many rows in another table, typically implemented using a join (or junction) table.
  *Example: students enrolled in multiple courses.*

Understanding these relationships is key to designing schemas and asking effective natural language questions about your data.

### Assignment: Relational Databases

Use [SQL Playground](https://sql-playground.dahvc.org/) to build your SQLite database, work with your data through natural language prompts, and create visualizations.

#### Step 1: Conduct Field Research

Conduct field research to collect **original source data**. The nature of the data is up to you. For example, you could:

* Conduct an interview and use text analysis tools to count word usage.
* Collect and analyze news headlines for political bias.
* Catalog sentiment types in an Instagram feed.

#### Step 2: Create the Database

Open **SQL Playground**, select **Add database (+)**, and choose **Local SQLite** to create an empty database. Give it a name related to your research. Make sure a model is selected in the chat controls and **Read-only** is turned off so you can create tables and add data.

#### Step 3: Create the Schema

Use the **chat sidebar** to describe the structure of your SQLite database in natural language. Think about:

* What tables you need.
* The columns in each table.
* How tables relate to each other: one-to-one, one-to-many, or many-to-many.

Review the proposed SQL and approve it when prompted. Open the **ERD** tab to inspect your tables, columns, and relationships.

#### Step 4: Add Data

Once the schema exists, provide the data you collected in the chat and ask the assistant to insert it into the appropriate tables. Review and approve the proposed SQL when prompted, then use the **Data** tab to check the records. If your data is already in a CSV file, you can also import it into an existing table from the Data tab.

#### Step 5: Visualize Data

Ask questions about your data in SQL Playground's chat, then ask it to turn the query results into a chart using its built-in **Chart.js** visualization tool. Specify what you want to compare and the chart type. Open the **Chart** tab to review the visualization.

Create **at least one meaningful visualization**, accompanied by a written summary of your data. Aim for visuals that answer real questions, such as:

* **Counts or distributions** – How often do particular words or sentiment types appear?
* **Relationships between entities** – How do interview participants relate to the topics they discuss?
* **Trends or comparisons** – What differences stand out across sources, categories, or time periods?

#### Step 6: Summarize Your Findings

Briefly explain what your visualizations show and what you learned from your data.

#### Step 7: Export Your Work

In SQL Playground, choose **three dots (…) → Backup** to download your complete database as a **.sqlite3** file containing both the schema and data. Use **Export chart** in the Chart tab to download your visualizations as **PNG** images.

## 2. Vector Databases

### What are Vector Databases?

Vector databases store and search **vectors**, which are lists of numbers. In text applications, an **embedding model** converts text into vectors that represent aspects of its meaning, allowing a search to find related passages even when they use different words.

Key concepts include:

* **Embeddings** – numerical representations of content produced by a model.
* **Chunks** – smaller passages of a document that can be embedded and retrieved individually.
* **Metadata** – information attached to each chunk, such as its source, page number, or topic.
* **Similarity search** – finding vectors close to a query vector using a measure such as cosine similarity.
* **Top-k retrieval** – returning the best k matches from a search, where k is a chosen number of results.

### How Vector Databases Fit into RAG Pipelines

**Retrieval-Augmented Generation (RAG)** supplies a language model with retrieved information to help it answer a question. A typical vector-based RAG pipeline has two stages:

* **Preparing the data** – Split documents into chunks, create embeddings, and store them with the text or a reference to it, plus source metadata.

* **Answering a question** – Embed the question using the same embedding model, retrieve similar chunks, and include their text in the language model's prompt. The model uses this context to generate an answer.

### Assignment: Vector Databases

Use [RAG Playground](https://rag-playground.dahvc.org/) to practice **indexing, chunking, and retrieving text, images, and audio**. Create **at least two projects** that explore different sources or indexing techniques.

#### Step 1: Create Projects and Index Sources

Use the **project menu in the top-left corner** to create and name each project. Choose an embedding model that supports the media types you want to index.

Experiment with different ways of bringing source material into your projects:

* **Upload files directly** – Add text, image, and audio files from your device.
* **Import a IIIF manifest** – Use [Pictor](https://tomdeneire.github.io/pictor/) to discover IIIF manifests. Copy a manifest URL into RAG Playground's **IIIF manifest** input, inspect its contents, and import the media you want to index.
* **Capture live images and audio** – Open **Mobile capture**, pair your phone with the desktop using the pairing code, and use your phone's camera and microphone to collect material.

#### Step 2: Experiment with Chunking

Explore how different settings change the indexed items:

* **Text** – Compare chunking strategies, chunk sizes, and overlap.
* **Images** – Compare indexing whole images with adding detail tiles.
* **Audio** – Experiment with the length and overlap of audio segments.

After changing settings, **reindex the stored sources** to apply those changes to existing material. Inspect the node graph to see how the indexed items are distributed.

#### Step 3: Retrieve and Compare

Try text, image, and audio queries supported by your selected model. Inspect the retrieved items and their similarity scores. Consider which results are relevant, what information is lost or preserved by chunking, and how the node graph changes across your experiments.

#### Step 4: Export Projects and Capture Screenshots

Export **at least two projects**. For each project:

* Open the **top-left project menu** and choose **Export current project** to download its zip file.
* Capture **screenshots of the node graph** that show your indexed material.

## 3. Submission Checklist

Upload the following files from both assignments to **one Box folder**:

* Your **SQLite database file (.sqlite3)** containing the schema and collected data.
* **PNG exports of at least one meaningful data visualization**.
* A **written summary of your insights**, explaining what each visualization shows and what you learned.
* **At least two RAG Playground project exports**.
* **Node graph screenshots for each RAG project**.

Make sure the folder's sharing settings allow access to the files. Submit **one Box folder share link to Canvas**.
