#  Big Data ESE 
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/Sem_3_Notes.git)

# Table of Contents
- [Big Data ESE](#big-data-ese)
- [Table of Contents](#table-of-contents)
  - [Previous Year Questions](#previous-year-questions)
      - [**1. Data Ingestion Layer**](#1-data-ingestion-layer)
      - [**2. Data Storage Layer**](#2-data-storage-layer)
      - [**3. Data Processing Layer**](#3-data-processing-layer)
      - [**4. Data Analytics Layer**](#4-data-analytics-layer)
      - [**5. Data Visualization and Access Layer**](#5-data-visualization-and-access-layer)
      - [**Integration Across Layers**](#integration-across-layers)
    - [**Block Placement Strategy**](#block-placement-strategy)
    - [**Example**](#example)
      - [**Block Placement**:](#block-placement)
    - [**Key Considerations**](#key-considerations)
      - [1. **NameNode**](#1-namenode)
      - [2. **DataNode**:](#2-datanode)
      - [3. **Block**:](#3-block)
      - [**Definition of Data Streams**](#definition-of-data-streams)
      - [**Challenges Faced by Data Streams**](#challenges-faced-by-data-streams)
      - [**Applications of Data Streams**](#applications-of-data-streams)
        - [1. **Fraud Detection in Financial Systems**](#1-fraud-detection-in-financial-systems)
        - [2. **IoT Sensor Monitoring**](#2-iot-sensor-monitoring)
      - [DGIM ( Datar-Gionis-Indyk-Motwani)](#dgim--datar-gionis-indyk-motwani)
      - [**Working of DGIM Method**](#working-of-dgim-method)
        - [**Example**](#example-1)
      - [**Advantages**](#advantages)
  - [](#)
      - [**Step 1: Find Frequent Itemsets**](#step-1-find-frequent-itemsets)
      - [**Step 2: Compute Confidence for the Rules**](#step-2-compute-confidence-for-the-rules)
      - [**Confidence Calculations**](#confidence-calculations)
        - [Definitions](#definitions)
        - [Given Sentences:](#given-sentences)
        - [a) **Shingles with (k=2) for each of D1 and D2**](#a-shingles-with-k2-for-each-of-d1-and-d2)
        - [b) **Shingles with (k=2) for D1 ∪ D3**](#b-shingles-with-k2-for-d1--d3)
        - [c) **Shingles with (k=3) at the character level for D1 ∪ D2**](#c-shingles-with-k3-at-the-character-level-for-d1--d2)
      - [Final Results:](#final-results)
    - [**MinHashing Algorithm**](#minhashing-algorithm)
    - [**Algorithm Steps**:](#algorithm-steps)
      - [**1. Input**:](#1-input)
      - [**2. Output**:](#2-output)
      - [**3. Steps**:](#3-steps)
    - [**Pseudocode**:](#pseudocode)
    - [**Task Scheduling in MapReduce**](#task-scheduling-in-mapreduce)
      - [**1. Components Involved in Scheduling**](#1-components-involved-in-scheduling)
      - [**2. Steps in Task Scheduling**](#2-steps-in-task-scheduling)
      - [**a) Job Initialization**](#a-job-initialization)
      - [**b) Scheduling Map Tasks**](#b-scheduling-map-tasks)
      - [**c) Scheduling Reduce Tasks**](#c-scheduling-reduce-tasks)
      - [**d) Handling Failures**](#d-handling-failures)
      - [**3. Types of Scheduling**](#3-types-of-scheduling)
      - [**a) FIFO Scheduler**:](#a-fifo-scheduler)
      - [**b) Fair Scheduler**:](#b-fair-scheduler)
      - [**c) Capacity Scheduler**:](#c-capacity-scheduler)
      - [**4. Optimizations in Scheduling**](#4-optimizations-in-scheduling)
    - [**Example**:](#example-2)
      - [Map Phase:](#map-phase)
      - [Shuffle and Sort Phase:](#shuffle-and-sort-phase)
      - [Reduce Phase:](#reduce-phase)
      - [Final Output:](#final-output)
      - [**Relational Algebra**](#relational-algebra)
      - [**1. Map Task Failures**](#1-map-task-failures)
        - [**Causes of Map Task Failures**](#causes-of-map-task-failures)
        - [**Handling Mechanisms**](#handling-mechanisms)
      - [**2. Job Failures**](#2-job-failures)
        - [**Causes of Job Failures**](#causes-of-job-failures)
        - [**Handling Mechanisms**](#handling-mechanisms-1)
    - [**Pig Architecture Components**](#pig-architecture-components)
    - [**Diagram: Pig Architecture**](#diagram-pig-architecture)
  - [Other questions](#other-questions)
      - [Working](#working)
  - [Pig hive PPT](#pig-hive-ppt)
    - [MapReduce](#mapreduce)
    - [Pig](#pig)
      - [Applications of Apache Pig](#applications-of-apache-pig)
    - [Apache Pig vs MapReduec](#apache-pig-vs-mapreduec)
    - [Flajolet Martin algorithm](#flajolet-martin-algorithm)
      - [Stepwise Solution](#stepwise-solution)
      - [Advantages](#advantages-1)
      - [Disadvantages](#disadvantages)
      - [Bloom Filter](#bloom-filter)
      - [False Positives Analysis](#false-positives-analysis)


## Previous Year Questions

Q1. a. **Discuss the functions of each of the five layers in Big Data architecture design.**

Ans. 
Big Data architecture typically involves five key layers that work together to process, store, and analyze vast amounts of data. Here's a detailed breakdown of the functions of each layer:

---

#### **1. Data Ingestion Layer**
   - **Function**: Responsible for collecting and importing data from various sources into the Big Data system.
   - **Key Features**:
     - Supports batch data ingestion (periodic imports) and real-time streaming.
     - Handles data from structured, semi-structured, and unstructured sources, such as databases, APIs, IoT devices, logs, and social media.
     - Includes mechanisms for error handling, data filtering, and format conversion.
   - **Examples**:
     - Tools: Apache Kafka, Apache Flume, Apache NiFi, AWS Kinesis.
     - Sources: Relational databases, sensors, files, or message queues.

---

#### **2. Data Storage Layer**
   - **Function**: Ensures the ingested data is stored in a secure and scalable manner, making it accessible for processing.
   - **Key Features**:
     - Accommodates the storage of structured, semi-structured, and unstructured data.
     - Provides distributed and fault-tolerant storage to prevent data loss.
     - Optimized for both long-term storage and quick retrieval for processing.
   - **Examples**:
     - Hadoop Distributed File System (HDFS), AWS S3, Google Cloud Storage.
     - NoSQL Databases: MongoDB, Cassandra, HBase.
     - Relational Databases: MySQL, PostgreSQL.

---

#### **3. Data Processing Layer**
   - **Function**: Processes the raw data to transform it into a usable format for analysis or storage.
   - **Key Features**:
     - Supports **batch processing** for large-scale data transformations and **real-time processing** for immediate insights.
     - Includes operations like filtering, sorting, aggregating, and cleaning.
     - Implements distributed computing to process data efficiently at scale.
   - **Examples**:
     - Batch Processing: Apache Hadoop (MapReduce), Apache Spark.
     - Real-Time Processing: Apache Flink, Apache Storm.

---

#### **4. Data Analytics Layer**
   - **Function**: Extracts insights, patterns, and intelligence from processed data.
   - **Key Features**:
     - Performs advanced analytics such as machine learning, predictive modeling, and statistical analysis.
     - Supports querying, reporting, and data mining.
     - Provides APIs or tools for analysts and data scientists to explore and experiment.
   - **Examples**:
     - Tools: Apache Spark (MLlib), TensorFlow, Python libraries (Pandas, Scikit-learn).
     - BI Platforms: Tableau, Power BI, QlikView.

---

#### **5. Data Visualization and Access Layer**
   - **Function**: Makes the insights accessible and interpretable for business users and decision-makers.
   - **Key Features**:
     - Generates dashboards, reports, and visual representations of data such as charts, graphs, and maps.
     - Provides interfaces for querying data interactively (e.g., SQL-like interfaces).
     - Ensures data is accessible via APIs for integration with external systems.
   - **Examples**:
     - Visualization Tools: Tableau, Kibana, Power BI.
     - Data Access: RESTful APIs, SQL-on-Hadoop tools like Hive or Impala.

---

#### **Integration Across Layers**
- These layers work seamlessly together in a pipeline:
  1. **Data Ingestion Layer** collects data.
  2. **Data Storage Layer** organizes and stores the data.
  3. **Data Processing Layer** transforms raw data into usable formats.
  4. **Data Analytics Layer** generates insights from the processed data.
  5. **Data Visualization and Access Layer** delivers the insights in a user-friendly way.

--- 

Q1. b. **Explain the nature of data and it's application**

Ans. 
1. **Data Complexity**: In healthcare, Big Data analytics can integrate complex patient records, medical images, and genetic data to provide personalized treatment plans and predict disease outbreaks.
2. **Data Uniqueness**: Social media platforms leverage the unique nature of user-generated content to provide personalized recommendations, targeted advertising, and sentiment analysis for business insights.
3. **Data Temporality**: Financial institutions use real-time data feeds to detect fraudulent transactions, monitor stock market fluctuations, and adjust investment strategies swiftly.
4. **Data Immutability**: Legal and compliance departments use immutable data logs for auditing purposes, ensuring the integrity and traceability of financial transactions, legal contracts, and regulatory compliance.
5. **Data Bias**: Data bias in criminal justice refers to using Big Data to analyse past arrest and sentencing information to find and fix unfair patterns in law enforcement and judicial decision-making.

---

Q1. c. **With an example, explain the strategy for placement of blocks in HDFS.**

Ans. 
The **placement of blocks in HDFS (Hadoop Distributed File System)** follows specific strategies to ensure reliability, fault tolerance, and efficient data access. Files in HDFS are divided into **blocks** (default size: 128 MB) and replicated across the cluster (default replication factor: 3). Here's an explanation with an example:

---

### **Block Placement Strategy**
1. **First Replica**:
   - Placed on the **same node** where the client writes the data (local write) if possible. This minimizes network usage.
   
2. **Second Replica**:
   - Placed on a **different rack** to ensure data availability even if a rack fails. This improves fault tolerance.
   
3. **Third Replica**:
   - Placed on a **different node in the same rack** as the second replica, balancing fault tolerance and network efficiency.

4. **Subsequent Replicas**:
   - For replication factors greater than 3, replicas are distributed across nodes and racks for increased redundancy.

---

### **Example**
- **File**: A 384 MB file is uploaded to HDFS.
- **Block Division**: File is split into three blocks: B1, B2, B3 (each 128 MB).
- **Replication Factor**: 3.

#### **Block Placement**:
1. **Block B1**:
   - **Replica 1**: Node N1 on Rack R1.
   - **Replica 2**: Node N2 on Rack R2.
   - **Replica 3**: Node N3 on Rack R2.

2. **Block B2**:
   - **Replica 1**: Node N4 on Rack R1.
   - **Replica 2**: Node N5 on Rack R2.
   - **Replica 3**: Node N6 on Rack R2.

3. **Block B3**:
   - **Replica 1**: Node N7 on Rack R1.
   - **Replica 2**: Node N8 on Rack R2.
   - **Replica 3**: Node N9 on Rack R2.

---

### **Key Considerations**
- **Data Locality**:
  - The first replica ensures faster access for the client by being stored locally.
- **Rack Awareness**:
  - Placing replicas on different racks minimizes data loss in case of rack failures.
- **Load Balancing**:
  - Replicas are spread across nodes to avoid overloading specific machines.

This strategy ensures HDFS achieves high reliability, fault tolerance, and optimized data access.

---

Q1. d. **With a neat diagram explain the HDFS architecture and its working.**

Ans. 
![alt text](image-8.png)

#### 1. **NameNode**
- The NameNode runs on commodity hardware with the GNU/Linux operating system and the NameNode software.
- It acts as the master server and performs the following tasks:
- Manages the file system namespace.
- Regulates client access to files.
- Executes file system operations such as renaming, closing, and opening files and directories.

#### 2. **DataNode**:
- Each DataNode also runs on commodity hardware with the GNU/Linux operating system and the DataNode software.
- For every node in the cluster, there will be a corresponding DataNode.
- DataNodes manage data storage and perform the following operations:
- Handle read-write operations on the file system based on client requests.
- Execute block creation, deletion, and replication according to instructions from the NameNode.
  
#### 3. **Block**:
- User data in HDFS is stored in files, which are divided into segments known as blocks.
- Each block represents the minimum amount of data that HDFS can read or write.
- The default block size is 64 MB, but it can be adjusted based on specific needs through HDFS configuration.

---

Q2. a. **Define data streams. Bring out the challenges faced by data streams. Giveany two application of data stream.**

Ans. 
#### **Definition of Data Streams**
A **data stream** is a continuous, real-time, and potentially infinite flow of data generated from various sources, such as sensors, log files, financial transactions, social media, or IoT devices. Unlike static datasets, data streams are dynamic and require immediate processing to extract valuable insights.

---

#### **Challenges Faced by Data Streams**
1. **High Velocity and Volume**:
   - Data streams arrive at high speed and in large quantities

2. **Infinite Nature**:
   - Their theoretically indefinite nature makes storing it all impractical.

3. **Real-Time Processing**:
   - To understand the data it needs immediate processing, which can be computationally demanding.

4. **Data Heterogeneity**:
   - Streams may consist of structured, semi-structured, and unstructured data.

5. **Handling Data Quality**:
   - Streams may include noisy, missing, or corrupted data.

6. **Fault Tolerance**:
   - Ensuring reliability in case of  node or network failures is important.
7. **Limited Memory**:
   - Processing systems will have limited memory and hence we need to use methods like **windowing**, etc.

8. **Out-of-Order Data**:
   - Events might not arrive in the sequence they occurred, complicating analysis and aggregation.

9. **Security and Privacy**:
   - Streams often contain sensitive information, requiring secure transmission and processing.

10. **Scalability**:
    - Systems must scale seamlessly to accommodate fluctuating stream loads.

---

#### **Applications of Data Streams**

##### 1. **Fraud Detection in Financial Systems**
   - **Description**: Real-time monitoring of financial transactions to identify and flag unusual or fraudulent activities.
   - **Example**: Credit card companies using streaming data to detect and prevent fraudulent transactions.

##### 2. **IoT Sensor Monitoring**
   - **Description**: Continuous monitoring of IoT devices and sensors for applications like predictive maintenance, environmental monitoring, or smart homes.
   - **Example**: Smart thermostats analyzing temperature and humidity data in real time to adjust settings automatically.


---

Q2. b. **Briefly explain the working of DGIM method. If needed, explain with an example for the same.**

Ans. 

#### DGIM ( Datar-Gionis-Indyk-Motwani)
The **DGIM (Datar-Gionis-Indyk-Motwani)** method is used to estimate the number of 1s in the last $n$ bits of a binary stream using limited memory. It operates by maintaining a compact summary of the stream using **buckets**.

---

#### **Working of DGIM Method**
1. **Stream Bucketing**:
   - Group 1s into *buckets*, each represented by its size and timestamp of the most recent 1.

2. **Bucket Rules**:
   - Each bucket has a size that is a power of 2 (e.g., 1, 2, 4, ...).
   - Maintain at most two buckets of each size for efficiency.
   - Buckets merge when a third bucket of the same size is created.

3. **Updating Buckets**:
   - On a new bit:
     - If it's 0: Do nothing.
     - If it's 1: Create a new bucket of size 1 with the current timestamp.
     - Merge buckets if needed to adhere to the two-bucket rule.

4. **Query Estimation**:
   - To estimate the number of 1s in the last $n$ bits:
     - Sum the sizes of buckets within $n$ bits.
     - Include the *partial contribution* of the oldest bucket if it extends beyond $n$.

---

##### **Example**
Consider a binary stream: `101101`.

1. **Step 1**:
   - First bit (1): Create bucket [1, t1].
   - Second bit (0): No action.
   - Third bit (1): Create bucket [1, t3].
   
2. **Step 2 (Merge)**:
   - Two size-1 buckets: Merge them into [2, t3].

3. **Step 3 (Continued Stream)**:
   - Process additional bits, creating and merging buckets as per rules.

---

#### **Advantages**
- Memory-efficient with $O(\log n)$ buckets.
- Approximate results with bounded error (at most 50%).

The DGIM method effectively tracks recent 1s in streams where exact counting is impractical.

![alt text](image-9.png)
---

Q2. c. **Describe the various ways of sampling the data streams. Explain the why sampling is important here.**

Ans. 

---

Q3. a. **Apply the aprori algorithm for discovering frequent item sets to the following datasets: (support value is 2 )**

| TransID | item Purchased | 
| -- | -- |
| 101 | Kiwi, Grapes, Star fruit | 
| 102 | Kiwi, Gooseberry | 
| 103 | Star fruit, Gooseberry |
| 104 | Kiwi, Grapes, Star fruit, lemon | 
| 105 | Lemon, Starfruit |
| 106 | Kiwi, Grapes, Star fruit | 

Check which of the following rules can be selected (if mininum confidence is 60%)
a) $\{Kiwi, Graphes\}.->\{ Kiwi, Grapes, Starfruit\}$
b) $\{Kiwi\} ->\{Grapes, Starfruit\}$ 
c) $\{Grapes\} -> \{Starfruit, Kiwi\}$
Ans. 

> Youtube video Reference : https://www.youtube.com/watch?v=zi_ydmbWfAs

#### **Step 1: Find Frequent Itemsets**
1. **Transactions**:
   $\begin{aligned}
   &T101: \{Kiwi, Grapes, Starfruit\} \\
   &T102: \{Kiwi, Gooseberry\} \\
   &T103: \{Starfruit, Gooseberry\} \\
   &T104: \{Kiwi, Grapes, Starfruit, Lemon\} \\
   &T105: \{Lemon, Starfruit\} \\
   &T106: \{Kiwi, Grapes, Starfruit\}
   \end{aligned}$

2. **Candidate Generation**:
   - Count occurrences of single items, pairs, and larger sets to find those meeting the support threshold ($ \text{support} \geq 2$).

| **Itemsets**          | **Support Count** |
|------------------------|--------------------|
| $\{Kiwi\}$          | 4                 |
| $\{Grapes\}$        | 3                 |
| $\{Starfruit\}$     | 5                 |
| $\{Lemon\}$         | 2                 |
| $\{Gooseberry\}$    | 2                 |
| $\{Kiwi, Grapes\}$  | 3                 |
| $\{Kiwi, Starfruit\}$ | 4                 |
| $\{Grapes, Starfruit\}$ | 3              |
| $\{Kiwi, Grapes, Starfruit\}$ | 3       |

Thus, frequent itemsets include all combinations with support $\geq 2$.

---

#### **Step 2: Compute Confidence for the Rules**
- **Confidence Formula**:
 $ \text{Confidence}(\{A\} \to \{B\}) = \frac{\text{Support}(\{A \cup B\})}{\text{Support}(\{A\})}
   \]
Thank you for pointing that out. If $\{Kiwi, Starfruit\}$ occurs only **3 times**, I'll recalculate the confidence for the rules based on this correction.

---

#### **Confidence Calculations**

(a) $\{Kiwi, Grapes\} \to \{Kiwi, Grapes, Starfruit\}$
- $\text{Support}(\{Kiwi, Grapes, Starfruit\}) = 3$
- $\text{Support}(\{Kiwi, Grapes\}) = 3$
- $\text{Confidence} = \frac{3}{3} = 100\%$
- **Selected** (Confidence $\geq 60\%$).

---

(b) $\{Kiwi\} \to \{Grapes, Starfruit\}$
- $\text{Support}(\{Kiwi, Grapes, Starfruit\}) = 3$
- $\text{Support}(\{Kiwi\}) = 4$
- $\text{Confidence} = \frac{3}{4} = 75\%$
- **Selected** (Confidence $\geq 60\%$).

---

(c) $\{Grapes\} \to \{Starfruit, Kiwi\}$
- $\text{Support}(\{Kiwi, Grapes, Starfruit\}) = 3$
- $\text{Support}(\{Grapes\}) = 3$
- $\text{Confidence} = \frac{3}{3} = 100\%$
- **Selected** (Confidence $\geq 60\%$).

Rules **(a)**, **(b)**, and **(c)** are still valid as they meet the minimum confidence threshold of 60%.

> Similarly you can calculate various condience rules for all the 2 and 3-itemsets ( you will get a total of 10 valid rules)

---

Q3. b. **Consider the following sentences**
**D1: I am writing.**
**D2: Sam is writing assignment.**
**D3: I could solve all questions of assignment.** **Calculate Jaccard's similarity for following**
a) Shingles with (k-2) for each of $D1, D2$ 
b) Shingles with (k=2) for $D1 U D3$
c) Shingles with (k-3) but at character level for D1 U D2 

Ans. 
To calculate the Jaccard's similarity for the given sets of shingle-based comparisons, we first need to define **shingles** and **Jaccard's similarity**.

##### Definitions
1. **Shingles**: A **shingle** is a contiguous subsequence of characters or words of length $k$. For example, given a string "writing", the 2-shingles (k=2) would be: "wr", "ri", "it", "ti", "in", "ng".
  
2. **Jaccard's Similarity**: The Jaccard Similarity between two sets $A$ and $B$ is defined as:
 $\text{Jaccard}(A, B) = \frac{|A \cap B|}{|A \cup B|}$
   where $|A \cap B|$ is the number of common shingles (intersection), and $|A \cup B|$ is the total number of unique shingles across both sets (union).

##### Given Sentences:
- **D1**: "I am writing."
- **D2**: "Sam is writing assignment."
- **D3**: "I could solve all questions of assignment."

Let's calculate the Jaccard's similarity for each part of the problem:

##### a) **Shingles with (k=2) for each of D1 and D2**

- **Shingles of D1 (k=2)**:
  - Sentence: "I am writing."
  - Shingles: ["I ", " a", "am", "m ", " w", "wr", "ri", "it", "ti", "in", "ng", "g."]

- **Shingles of D2 (k=2)**:
  - Sentence: "Sam is writing assignment."
  - Shingles: ["Sa", "am", "m ", " i", "is", "s ", " w", "wr", "ri", "it", "ti", "in", "ng", " a", "as", "ss", "si", "ig", "gn", "nm", "me", "en", "nt", "t."]

- **Jaccard's Similarity for D1 and D2**:
  - Intersection of shingles: ["am", "m ", " w", "wr", "ri", "it", "ti", "in", "ng"]
  - Union of shingles: 26 unique shingles (from D1 and D2 combined)
  
$\text{Jaccard}(D1, D2) = \frac{9}{26} \approx 0.346$

##### b) **Shingles with (k=2) for D1 ∪ D3**

- **Shingles of D1 (k=2)**: Already calculated above.
  
- **Shingles of D3 (k=2)**:
  - Sentence: "I could solve all questions of assignment."
  - Shingles: ["I ", " c", "co", "ou", "ul", "ld", "d ", " s", "so", "ol", "lv", "ve", "e ", " a", "al", "ll", "l ", " q", "qu", "ue", "es", "st", "ti", "io", "on", "ns", "s ", " o", "of", "f ", " a", "as", "ss", "si", "ig", "gn", "nm", "me", "en", "nt", "t."]

- **Jaccard's Similarity for D1 ∪ D3**:
  - Union of shingles from D1 and D3: 42 unique shingles.
  - Intersection of shingles: ["I ", " a", "am", "m ", " s", "so", "ol", "ve", "e ", " a", "al", "ll", "l ", " q", "qu", "ue", "es", "st", "ti", "io", "on", "ns", "s ", " o", "of", "f ", " a", "as", "ss"]
  
$\text{Jaccard}(D1 \cup D3) = \frac{15}{42} \approx 0.357$

##### c) **Shingles with (k=3) at the character level for D1 ∪ D2**

- **Shingles of D1 (k=3) at the character level**:
  - Sentence: "I am writing."
  - Shingles: ["I a", " am", "am ", "m w", " wr", "wri", "rit", "iti", "tin", "ing", "ng."]

- **Shingles of D2 (k=3) at the character level**:
  - Sentence: "Sam is writing assignment."
  - Shingles: ["Sam", "am ", "m i", " is", "is ", "s w", " wr", "wri", "rit", "iti", "tin", "ing", "ng ", "g a", " as", "ass", "ssi", "sig", "ign", "gn ", "n a", " as", "ass", "ssi", "sig", "ign", "gn ", "n t", "t."]

- **Jaccard's Similarity for D1 ∪ D2 (k=3)**:
  - Union of shingles from D1 and D2: 20 unique shingles.
  - Intersection of shingles: ["am ", "m w", " wr", "wri", "rit", "iti", "tin", "ing"]
  
$\text{Jaccard}(D1 \cup D2) = \frac{8}{20} = 0.4$


#### Final Results:
- **a)** Jaccard's similarity between D1 and D2 with (k=2): **0.346**
- **b)** Jaccard's similarity between D1 ∪ D3 with (k=2): **0.357**
- **c)** Jaccard's similarity between D1 ∪ D2 with (k=3) at the character level: **0.4**

---

Q3. c. **Give an algorithm to explain the working of min hashing Function.**

Ans. 
### **MinHashing Algorithm**

MinHashing is a technique used to approximate the **Jaccard Similarity** between two sets efficiently. The algorithm works by creating a signature (a small hash representation) for each set that preserves similarity. The steps below describe the process:

---

### **Algorithm Steps**:

#### **1. Input**:
- Two sets $A$ and $B$ to compare.
- A universal set $U$ containing all possible elements in $A$ and $B$.
- $k$: The number of hash functions to use.

#### **2. Output**:
- MinHash signatures for $A$ and $B$.
- Approximation of the Jaccard Similarity using the signatures.

#### **3. Steps**:

1. **Represent the Sets**:
   - Convert $A$ and $B$ into binary vectors or characteristic matrices.
   - Example:
     - $U = \{a, b, c, d\}$
     - $A = \{a, c\}$
     - $B = \{b, c, d\}$
     - Characteristic Matrix:
       | Element | Set $A$ | Set $B$ |
       |---------|------------|------------|
       | $a$ | 1          | 0          |
       | $b$ | 0          | 1          |
       | $c$ | 1          | 1          |
       | $d$ | 0          | 1          |

2. **Define Hash Functions**:
   - Choose $k$ random hash functions $h_1, h_2, ..., h_k$.
   - Each hash function maps elements in $U$ to integers (e.g., $h(x) = (ax + b) \mod p$, where $p$ is a large prime).

3. **Compute MinHash Values**:
   - For each hash function $h_i$ and each set $S$:
     - Apply $h_i$ to all elements in $S$.
     - Record the **minimum hash value** as the signature for $S$ under $h_i$.
   - Example:
     - Hash functions:
       - $h_1(x) = (2x + 1) \mod 5$
       - $h_2(x) = (3x + 2) \mod 5$
     - Hash values for elements:
       - $h_1(a) = 3, h_1(b) = 0, h_1(c) = 2, h_1(d) = 4$
       - $h_2(a) = 4, h_2(b) = 1, h_2(c) = 3, h_2(d) = 0$
     - MinHash signature for $A$:
       - For $h_1$: MinHash = $\min(\{h_1(a), h_1(c)\}) = 2$
       - For $h_2$: MinHash = $\min(\{h_2(a), h_2(c)\}) = 3$
     - Signature for $A$: \([2, 3]\)
     - Signature for $B$: \([0, 0]\)

4. **Estimate Jaccard Similarity**:
   - Compare the MinHash signatures for $A$ and $B$.
   - The similarity is the fraction of matching components in the signatures.
   - Example:
     - $\text{Signature of } A = [2, 3]$
     - $\text{Signature of } B = [0, 0]$
     - No matches, so estimated similarity = $0\%$.

---

### **Pseudocode**:
```text
Input: Sets A, B; k hash functions
Output: MinHash signatures for A and B

1. Initialize signature matrices MinSig_A[k] and MinSig_B[k] with ∞.
2. For each hash function h_i (i = 1 to k):
      For each element x in A:
          Compute h_i(x)
          Update MinSig_A[i] = min(MinSig_A[i], h_i(x))
      For each element x in B:
          Compute h_i(x)
          Update MinSig_B[i] = min(MinSig_B[i], h_i(x))
3. Compute similarity as:
      Similarity = Number of matching entries in MinSig_A and MinSig_B / k
4. Return MinSig_A, MinSig_B, Similarity
```
---

Q4. a. **Explain how the tasks are schedule in Map Reduce.**

Ans. 
### **Task Scheduling in MapReduce**

In the MapReduce framework, task scheduling ensures efficient execution of map and reduce tasks on distributed nodes. It focuses on maximizing resource utilization, minimizing execution time, and handling failures effectively. Below is an explanation of how tasks are scheduled in MapReduce:

---

#### **1. Components Involved in Scheduling**
- **JobTracker** (Master Node):
  - Receives job requests from the client.
  - Splits the job into tasks (map and reduce).
  - Assigns tasks to TaskTrackers and monitors their progress.
- **TaskTracker** (Worker Nodes):
  - Executes map and reduce tasks assigned by the JobTracker.
  - Reports task status (success, failure, or progress) to the JobTracker.

---

#### **2. Steps in Task Scheduling**

#### **a) Job Initialization**
- **Job Input Split**: The JobTracker splits input data into smaller chunks called input splits.
- **Task Creation**:
  - One **map task** is created for each input split.
  - The number of **reduce tasks** is determined by the job configuration.

---

#### **b) Scheduling Map Tasks**
1. **Data Locality**:
   - Map tasks are scheduled on TaskTrackers that have the input split locally.
   - If no local TaskTracker is available, the task is scheduled on a node in the same rack or nearby.
   - **Reason**: Reduces network overhead by utilizing data locality.
   
2. **Task Assignment**:
   - JobTracker checks TaskTrackers for available map slots.
   - Idle slots are allocated to tasks from the task queue.
   
3. **Speculative Execution**:
   - If a map task is running slower than expected, a speculative copy is executed on another TaskTracker to avoid delays.

---

#### **c) Scheduling Reduce Tasks**
1. **Shuffle and Sort Phase**:
   - Reduce tasks start fetching intermediate map outputs from completed map tasks.
   - Scheduling reduce tasks before all map tasks complete ensures overlap of shuffle/sort and map execution phases.

2. **Task Assignment**:
   - JobTracker assigns reduce tasks to TaskTrackers with idle reduce slots.
   - Data locality is less important for reduce tasks since they must pull data from multiple nodes.

---

#### **d) Handling Failures**
1. **Map Task Failure**:
   - If a map task fails, the JobTracker reschedules the task on another TaskTracker.
   - The task is re-executed using the same input split.

2. **Reduce Task Failure**:
   - If a reduce task fails, the JobTracker reassigns it to another TaskTracker.
   - Intermediate outputs from map tasks are fetched again.

3. **Node Failure**:
   - If a TaskTracker fails, all tasks running on it are reassigned to other nodes.
   - Any lost intermediate outputs are recomputed by re-running affected map tasks.

---

#### **3. Types of Scheduling**

#### **a) FIFO Scheduler**:
- Tasks are scheduled in the order they are submitted.
- Simple but may lead to resource underutilization.

#### **b) Fair Scheduler**:
- Ensures all jobs get a fair share of cluster resources.
- Useful in multi-user environments.

#### **c) Capacity Scheduler**:
- Resources are divided into queues, each with a guaranteed capacity.
- Ideal for large-scale shared clusters.

---

#### **4. Optimizations in Scheduling**
- **Data Locality**: Prioritizing task execution on nodes with data ensures minimal data transfer.
- **Speculative Execution**: Resolves stragglers, improving performance.
- **Backup Tasks**: Duplicate tasks are created to avoid delays caused by slow nodes.

---

### **Example**:
For a 100 MB input file split into 10 chunks (10 MB each):
1. 10 map tasks are created, each processing one split.
2. The JobTracker assigns these tasks to TaskTrackers based on data locality.
3. Once all map tasks finish, the shuffle and reduce phases begin, with reduce tasks fetching intermediate outputs.
4. Reduce tasks merge data and produce the final output.

This efficient task scheduling ensures distributed processing and fault tolerance in MapReduce.

---

Q4. b.**Write in detail the concept of developing the Map Reduce Application to find the occurrences of a word.**

Ans.
The MapReduce algorithm is a parallel data processing framework that efficiently processes large datasets by dividing them into smaller chunks and distributing the processing across a cluster of computers. Let's elaborate on the MapReduce algorithm with an example:

**Problem Statement**: Suppose we have a large collection of text documents, and we want to
count the frequency of each word across all documents.
#### Map Phase:
• In the Map phase, we break down the problem into smaller tasks.
• Each task is responsible for processing a portion of the input data.
• We define a map function that takes an input record (in this case, a document) and emits key-value pairs.
• The key represents a word in the document, and the value is set to 1 to indicate that the word was encountered once in this document.
**Eg.**
Input: "Hello world! Hello MapReduce."
Output:
("Hello", 1)
("world!", 1)
("Hello", 1)
("MapReduce", 1)

#### Shuffle and Sort Phase:
• After the Map phase, the framework collects all emitted key-value pairs and performs a shuffle and sort operation.
• During this phase, all key-value pairs with the same key are grouped together and sorted.
• This is essential to ensure that all occurrences of a word are processed together in the Reduce phase.
**Eg.**
("Hello", [1, 1])
("MapReduce.", [1])
("world!", [1])


#### Reduce Phase:
• In the Reduce phase, we define a reduce function that takes a key and a list of values.
• The key represents a unique word, and the list of values contains the counts of that word
from different documents.
• The reduce function aggregates the values for each key to calculate the total frequency of
that word across all documents.
**Eg.**
Input for key "Hello": [1, 1]
Output: ("Hello", 2)
Input for key "MapReduce.": [1]
Output: ("MapReduce.", 1)
Input for key "world!": [1]
Output: ("world!", 1)

#### Final Output:
**("Hello", 2)**
**("MapReduce.", 1)**
**("world!", 1)**


---

Q4. c. **Explain the role of map and reduce to execute the following relational operations.**
a) Union
b) Intersection

Ans. 
MapReduce can be used for various functions due to it's parallel computing efficiency as well as file storage redundancy and fault tolerance. 

#### **Relational Algebra**
One of it's applications is **Relational Algebra**, i.e., many traditional databases involve retrieval of small amounts of data, even though the database itself may be large 
1. **Selection**: Apply a condition C to each tuple in the relation and produce as output only those tuples that satisfy C. The result of this selection is denoted σC (R).
2. **Projection**: For some subset S of the attributes of the relation, produce from each tuple only the components for the attributes in S. The result of this projection is denoted πS(R).
3. **Union, Intersection, and Difference**: These well-known set operations apply to the sets of tuples in two relations that have the same schema.

First, consider the union of two relations. Suppose relations R and S have the same schema. Map tasks will be assigned chunks from either R or S; it doesn’t matter which. The Map tasks don’t really do anything except pass their input tuples as key-value pairs to the Reduce tasks. The latter need only eliminate duplicates as for projection.
**The Map Function**: Turn each input tuple $t$ into a key-value pair $(t, t)$.
**The Reduce Function**: Associated with each key t there will be either one or two values. Produce output $(t, t)$ in either case.

To compute the intersection, we can use the same Map function. However, the Reduce function must produce a tuple only if both r task for $t$ should produce $(t, t)$. However, if the value-list associated with key $t$ is just $[t]$, then one of $R$ and $S$ is missing $t$, so we don’t want to produce a tuple for the intersection.
**The Map Function**: Turn each tuple $t$ into a key-value pair $(t, t)$.
**The Reduce Function**: If key t has value list $[t, t]$, then produce $(t, t)$. Otherwise, produce nothing.

---

Q4. d. **How are failures handled in map reduce?**

Ans. 

- Data loss prevention
  - By keeping multiple copies of data in different machines
- Data movement minimization
  - By moving computation to the data
  - (send your computer program to machines containing data)
- Simple programming model
  - Mainly two functions
    - Map
    - Reduce
- Programmer’s responsibility
  - Write only two functions, map and reduce suitable for your problems
  - Do not worry about other things

#### **1. Map Task Failures**
Map task failures occur during the execution of map tasks, which process input data and generate intermediate key-value pairs.

##### **Causes of Map Task Failures**
1. **Hardware Failures**:
   - Node crashes, disk failures, or power outages.
2. **Software Issues**:
   - Bugs in user-defined map code (e.g., NullPointerException, runtime errors).
3. **Data Corruption**:
   - Input data is corrupted or unreadable.
4. **Timeouts**:
   - A map task takes too long without reporting progress (e.g., due to infinite loops or resource contention).

##### **Handling Mechanisms**
- **Task Retry**:
  - The failed map task is retried automatically on another node.
  - By default, tasks are retried up to four times in Hadoop (configurable).
- **Speculative Execution**:
  - If a map task is slow (but not yet failed), a duplicate task is launched on another node. The faster of the two completes, and the slower one is killed.
- **Data Replication**:
  - Input data in HDFS is replicated (default replication factor is 3). If a task fails due to corrupted data on one node, it is re-executed on another node using a healthy replica.
- **Timeout Recovery**:
  - If a map task fails to make progress within the timeout period, it is assumed to have failed and is rescheduled.

---

#### **2. Job Failures**
A **job failure** occurs when the entire MapReduce job cannot complete successfully. This could happen due to persistent map task failures or issues in the overall execution framework.

##### **Causes of Job Failures**
1. **Repeated Task Failures**:
   - A task exceeds the retry limit (e.g., persistent code bugs or corrupted input data).
2. **Resource Exhaustion**:
   - Insufficient memory, CPU, or disk space for tasks.
3. **Master Node Failures**:
   - The failure of the JobTracker (Hadoop 1.x) or ApplicationMaster (Hadoop 2.x/YARN).
4. **Input/Output Errors**:
   - Missing or inaccessible input data, or issues writing final output.
5. **Configuration Errors**:
   - Incorrect job configuration parameters.

##### **Handling Mechanisms**
- **Abort After Max Retries**:
  - If a task fails beyond its retry limit, the entire job is aborted. The failure is logged, and the user is notified.
- **Master Node Recovery**:
  - In YARN (Hadoop 2.x), the ApplicationMaster can restart and resume jobs using checkpointed progress.
- **Graceful Exit and Cleanup**:
  - Failed jobs ensure proper cleanup of temporary files and resources (e.g., intermediate data or reserved cluster slots).
- **User Notification**:
  - Detailed logs and error messages are provided to help users debug the failure.

---

Q5. a. **Explain the Pig architecture with the help of a diagram.**

Ans. 
Apache Pig is a platform for processing and analyzing large data sets. It provides a high-level scripting language, Pig Latin, that abstracts the complexity of MapReduce programming. Its architecture can be divided into several components, each playing a distinct role in the data processing pipeline.

### **Pig Architecture Components**

1. **Pig Latin Scripts**:
   - **Function**: Users write data transformation and processing logic in the Pig Latin scripting language. 
   - **Input**: High-level Pig Latin commands.

2. **Parser**:
   - **Function**: Checks the syntax and semantics of the Pig Latin script.
   - **Output**: A logical plan, representing the script as a directed acyclic graph (DAG) of logical operators.

3. **Optimizer**:
   - **Function**: Optimizes the logical plan by applying transformations like merging operators and reordering joins to improve efficiency.
   - **Output**: An optimized logical plan.

4. **Compiler**:
   - **Function**: Translates the optimized logical plan into a series of MapReduce jobs or other execution plans (e.g., Tez or Spark).
   - **Output**: Physical execution plan.

5. **Execution Engine**:
   - **Function**: Executes the physical plan on the underlying processing engine (typically Hadoop's MapReduce, Tez, or Spark).
   - **Input**: Physical plan generated by the compiler.
   - **Output**: Results of data processing.

6. **Hadoop Distributed File System (HDFS)**:
   - **Function**: Acts as the default storage for input and output data.
   - **Input**: Raw data files.
   - **Output**: Processed results, stored back in HDFS.

7. **Pig Interfaces**:
   - **Grunt Shell**: Interactive shell for executing Pig commands and scripts.
   
---

### **Diagram: Pig Architecture**


![alt text](image-6.png)

---

Q5. b. **Write the syntax for the following in Hive, explaining the various keywords and its roles.**
a) Alter Table
b) Load Table

Ans. 
**ALTER TABLE**
ALTER TABLE table_name 
[ADD | DROP ] [ IF EXISTS ] COLUMN column_name data_type [ COMMENT 'comment' ]
[RENAME TO new_table_name]

Example : ALTER TABLE mytable
ADD COLUMN email STRING COMMENT 'Email Address'
RENAME TO renamedtable 

**LOAD TABLE**
LOAD DATA [LOCAL] INPATH 'file_path' [OVERWRITE] INTO TABLE table_name [PARTITION (partition_column = value, ....)]

Example : LOAD DATA LOCAL INPATH "/path/to/data" OVERWRITE INTO TABLE mytable; 

**DROP TABLE**
sql
Copy code
DROP TABLE [IF EXISTS] table_name;
Example:
sql
Copy code
DROP TABLE IF EXISTS mytable;

**DROP SCHEMA**
DROP SCHEMA [IF EXISTS] schema_name [CASCADE];

Example:
DROP SCHEMA IF EXISTS myschema CASCADE;

**DROP DATABASE**
DROP DATABASE [IF EXISTS] database_name [CASCADE];

Example:
DROP DATABASE IF EXISTS mydatabase CASCADE;

---

Q5. c.  **Bring out the various file formats supported by Hive.**

Ans. 
In Hive, the storage format refers to how the data is stored physically on the underlying file system. Hive supports various file formats, and the choice of storage format can have an impact on performance, compression, and query processing. Some of the commonly used storage formats in Hive include:
1. **TextFile**:
TextFile is a plain text format where each line in the file represents a record. Fields within a record are typically delimited by a specific character, such as a comma or a tab.

*Pros*: Human-readable, simple, and easy to work with.
*Cons*: Inefficient for certain query types, lacks built-in compression, and may not be optimal for large- scale data processing.

2. **SequenceFile**:
SequenceFile is a binary file format used for storing key-value pairs. It is a common Hadoop file format that supports both compression and splitting.

*Pros*: Binary format for efficient storage and processing, supports compression, and is splittable for parallel processing.
*Cons*: Not human-readable.

3. **ORC (Optimized Row Columnar)**:
ORC is a columnar storage format designed for high performance. It organizes data by columns rather than rows, providing better compression and faster query processing.

*Pros*: Excellent compression, predicate pushdown (filters applied during read), and improved performance for analytical queries.
*Cons*: Not human-readable, may have slightly higher write times compared to other formats.

4. **Parquet**:
Parquet is a columnar storage format similar to ORC, designed to be highly efficient for both storage and processing. It is an open standard format supported by various big data processing frameworks.

*Pros*: Excellent compression, support for nested data structures, and good performance for analytical queries.
*Cons*: Not human-readable.

5. **Avro**:
Avro is a binary serialization format that supports schema evolution. It is row-based and allows for flexible schema changes over time.

*Pros*: Compact binary format, supports schema evolution, and can be used for serializing complex data structures.
*Cons*: Not as optimized for query performance as columnar storage formats.

---

Q5. d. **Explain the various Pig Latin data formats.**

Ans. 

---

## Other questions 

Q1. **What is Big Data ?**

Ans. 
Big Data refers to extremely large and complex datasets that cannot be effectively managed, processed, or analyzed using traditional data processing tools and methods.
They usually contain : 
1. Structured data 
2. Unstructured data 

From sources like **images, videos, sensor data, social media content, etc** 

Characteristics of Big Data:
1. **Volume**: Encompasses massive data amounts, often in petabytes.
2. **Velocity**: Data flows in real-time, from sources like IoT and social media.
3. **Variety**: Diverse data types include structured, unstructured, and semi-structured.
4. **Variability**: Data can be inconsistent, arriving irregularly.
5. **Complexity**: Inherent complexity arises from data interconnections and privacy

**Important tip** : These characteristics can double as challenges

--- 

Q2. **Explain the nature of data and it's applications**

Ans. 
1. **Data Complexity**: The data being collected can be highly complex since it's of different types like **text, audio, video, file formats, etc**
2. **Data Uniqueness**: big data usually uses unique and previously unused data sources to get **valuable insights**
3. **Data Temporality**: Financial institutions use real-time data feeds to detect fraudulent
4. **Data Immutability**: Some Big Data sets are immutable, meaning they cannot be changed once collected.
5. **Data Bias**: Bias in Big Data can be a concern, as data sources may not represent the entire population or may contain inherent biases.

---

Q2. **Explain structured, unstructured and semi structured data.**

Ans. 
1. **Structured Data** : 
   - Structured data is highly organized and follows a specific format or schema.
   - Usually found in RDBMS and have specific datatype filled rows and columns.
2. **Unstructured Data** :
   - Unstructured data lacks a specific structure or format.
   - It includes text, images, audio, video, and social media content.
3. **Semi-Strucutred Data**:
   - Semi-structured data falls between structured and unstructured data.
   - It has some level of structure, often in the form of tags, labels, or metadata, but it doesn't conform to a rigid schema like structured data.

---

Q3. **What is CAP theorem ?**

Ans.
The limitations of distributed databases can be described in the so called the **CAP theorem**

1. **Consistency**: every node always sees the same data at any given instance (i.e., strict consistency)

2. **Availabilit**y: the system continues to operate, even if nodes in a cluster crash, or some hardware or software parts are down due to upgrades

3. **Partition Tolerance**: the system continues to operate in the presence of network partitions

---

Q4. **What is a NoSQL Database?**

Ans.
- NoSQL Database is used to refer a non-SQL or non relational database.
- Mechanism for storage and retrieval of data other than tabular relations model
- It doesn't use tables for storing data
- Generally used to store big data and real-time web applications

---

Q4. **What is HDFS?**

Ans. 
Hadoop Distributed File System (HDFS) is the primary storage system used by Hadoop. It is a framework for processing and analyzing Big Data. HDFS is designed to store and manage large datasets across multiple machines while providing fault tolerance.

#### Working 
- It divides files into smaller blocks and distributes them accross a cluster of machines 
- Each block is replicated multiple times to ensure fault tolerance.
- The Master/Slave architecture includes a NameNode (master) for metadata management and DataNodes (slaves) for storing data.


---

## Pig hive PPT

Hadoop has 4 main languages used in it : 
1. **Java** : This is Hadoops native language ( Hadoop was written in Java)
2. **Pig** : This is the Query and Workflow language
3. **Hive**: This is the  SQL based Language 
4. **HBase** : Column Oriented database for MapReduce

--- 

### MapReduce 
MapReduce has a lot of real world appeal because of three mani factors : 
1. Scalability : It is highly scalable due to simpler design 
2. Affordability : Runs on cheap commodity hardware 
3. Procedural Control : A processing "pipe".

**Disadvantage**
1. Data Rigidity
2. Hand coding operations
3. Hidden Semantics 

Hence we need to use a higher level Data Flow language, i.e. **Pig Latin**

### Pig 
> What is Pig ? 
- It's a language developed by yahoo and a top level Apache project
- You can access data on a cluster using *Pig Latin* 
- It interprets Pig latin and generates MapReduce jobs that will run the cluster
- easy data summarization

#### Applications of Apache Pig 
1. To process huge data sources



---


### Apache Pig vs MapReduec

|Point | Apache pig | Map Reduce | 
| -- | -- | -- | 
| Type | Apache pig is a Data Flow language | Map Reduce is a data processing paradigm | 
| Language | High level lang | Low level lang and rigid | 
| Joins | Easy to perform a Join | hard to perform a Join b/w datasets | 
| Domain | Need basic SQL knowledge to use | Need high level Java knowledge | 
| LOC | Uses Multi-Query approach which reduecs LOC | Needs 20 times the LOC to perform same task | 
| Compilation | No need for compilation | Long Compilation process | 

---

### Flajolet Martin algorithm
It is used to approximate the number of unique elements ( 1 ) iin a data stream or Database in one pass 
- It uses less memory space when executing 

#### Stepwise Solution 
- Select a hash function **H** 
- Apply that hash functon to each data item in the dataset to get it's Binary representation 
- Finally we determine the right most zero in each binary string 
- $r(x) = \text { Length of trailing zeroes in h(x)}$
  

#### Advantages 
1. Scalability : 
   - It can tackle large datasets 
   - it efficiently estimates the count of unique elements without having to store the entire dataset in memory 
2. Memory efficiency : 
   - Demands minimal memory due to smart use of hash functions and bit manipulation
3. Speed : 
   - it's high speed amkes it suitable for real life applications
   - the algo is computationally efficient 


#### Disadvantages 
1. Accuracy
   - If a precision count is required then this algorithm is not accurate enough
2. Sensitive to dataset
   - Accuracy is influenced by the distribution and characteristics of the dataset 
3. Hash function selection 
   - Performance and accuracy is affected by the hash function used 
4. Limited applicability 
   - Can only identify the number of unique elements 

---

#### Bloom Filter 
It is a space efficient probabailitic data structure that is used to test if an item is a member of a set 

#### False Positives Analysis
If we have a bloom filter with $m$ bits and $k$ hash functions, the probability that a certain bit will still be zero after one insertion is 
![alt text](image-12.png)
Then, after $n$ insertions, the probability of it still being zero after $n$ insertions is
![alt text](image-11.png)
So, that means the probability of a false positive is 
![alt text](image-10.png)

![alt text](image-13.png)

Q. A bloom filter is composed of a bit array of 216 bits. We are told that the filter is designed to be optimally performing when there are 28 entries.

Given that the filter is filled with 28 entries, what is the expected number of queries one has to perform to perform to get a false positive?