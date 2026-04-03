Spark Ground Up: Data Engineering on Distributed Clusters
This repo is a structured deep-dive into Apache Spark, moving from the foundational RDDs to high-level architectural optimizations and real-time streaming.

This repository is a comprehensive guide to mastering Apache Spark, focusing on the transition from conceptual learning to production-grade execution on a multi-node Hadoop cluster.

🚀 Environment Specifications

The code in this repository is designed to run on a YARN-managed Spark cluster with the following specifications:

    Spark Version: 3.1.2
    Resource Manager: YARN
    Storage Layer: HDFS (Hadoop Distributed File System)
    Execution Mode: Client/Cluster mode via Gateway Node

📂 Data Architecture

To ensure successful execution across worker nodes, this project utilizes a tiered storage approach:

    Local Gateway (/home/username/): Local Linux file system.
    HDFS Landing Zone (/user/username/): The primary source for Spark distributed reads.
    Spark Warehouse (/user/username/warehouse/): The default location for Hive warehouse.


🗺️ The Roadmap
1. Fundamental RDDs (Low-Level API)
   
      Understanding the "Resilient Distributed Dataset" to master the internal mechanics of Spark.
* Transformations & Actions: Map, Filter, FlatMap vs. Collect, Count, Take, sortyBy.
* PairRDDFunctions: reduceByKey, groupByKey, and the importance of Map-side combining.
* Joins: Handling composite keys and the cost of shuffles.


2. High-Level APIs (DataFrames & Spark SQL)

      Transitioning to the Catalyst Optimizer and Tungsten Engine.
* Schema Enforcement: Using DDL strings and StructType vs. InferSchema.  
* Read Modes: PERMISSIVE (with _rescued_data), FAILFAST, and DROPMALFORMED.
*  Relational Operations: Joins, Aggregations, and Window Functions.


3. Spark Internals & Architecture

      How Spark actually works under the hood.
* Lifecycle: Driver vs. Executors, DAGs, Stages, and Tasks.
* Thin vs. Fat Executors: Finding the "Sweet Spot" (The 5-Core Rule).
* Memory Management: Storage vs. Execution memory and Off-heap storage.


4. Performance Tuning & Optimization

      The "Special Sauce" for production-grade pipelines.
* Adaptive Query Execution (AQE): Coalescing partitions, Skew Joins, and Local Shuffle Readers.
* Broadcast Joins: When to bypass the shuffle to save time and money.
* Delta Lake Optimizations: optimizeWrite and autoCompact.


5. Structured Streaming

      Processing data at the speed of business.
* Auto Loader (cloudFiles): Efficient file ingestion with schema evolution.
* Triggers: Continuous processing vs. availableNow=True for cost-efficient batch-style streaming.
* Check-pointing: Ensuring fault tolerance and exactly-once semantics.
