---
layout: post
title: Data Warehouse vs. Data Lake
subtitle: How does one differs from another
gh-repo: siddhartha-shrivastava
comments: true
---

In this post I will try to explain the difference between the commonly used term Data Warehouse and not so common term 'Data Lake' (Although Data Scientists/ ML Engineers are pretty familiar with it)

Big Data has been around for now almost a decade, but during last couple of years its importance has moved from being 'an advantage' to 'system critical' or business critical. In here, I will try my best to explain the difference between the two of them.

While I am currently working extensively with Medical datasets, which somebody took painful efforts to clean and curate, its often that, the data recieved by researchers is limited. As it may not fullfill from one to many criteria, thus may not make it to the database. 
While discussing with my couple of friends, regarding the data lake, I found that, most of the people think data lake is just an advnaced version of data warehouse with more functional capabilty and  functions to be executed, **which infact is not the case**.

**First and Foremost, Definitions!!**

### Data Warehouse
According to [Wikipedia](https://en.wikipedia.org/wiki/Data_warehouse):

“In computing, a data warehouse (DW or DWH), also known as an enterprise data warehouse (EDW), is a system used for reporting and data analysis, and is considered a core component of business intelligence.”

Apart from this, for quick pointers, we can understand that:


It is highly transformed and structured.

Data is defined for usage before loading the data warehouse.

And since, the data is defined beforhand for its purpose of use, it represents a biased picture 
**what it mean is, curated data used for e.g hospitality industry may represent something differnet about their customers than the data stored by Transportation industry**



**Data Lake**
One of the most layperson explaination which I got for the Data Lake was from the **Forbes** article, where they explained
“If you think of a datamart as a store of **bottled water** – cleansed and packaged and structured for easy consumption – the data lake is a large body of water in a more **natural state**. The contents of the data lake stream in from a source to fill the lake, and various users of the lake can come to examine, dive in, or take samples.”

Here, the **natural state & Bottled water** is a faboulous analogy which clearly explains the stark difference between Data Warehouse and Data Lake
FYI - Pentaho CTO James Dixon has generally been credited with coining the term “data lake”.

A data lake holds data in an unstructured or more natural way it was generated and there is no hierarchy or organization among the individual pieces of data unlike Data Warehouse. It holds data in its rawest form—it’s not processed or analyzed. Apart from being a **Universal data Accepter**, it supports data in all the bandwidths i.e in the most raw form (which can be a sparse data, a big headache) to the ready to use polished data. It supports all data types and Schemas as well.

So , we can say that:

All the data is accepted without any truncation or modification ; Data is stored in an untransformed or raw state.


Now, Lets quicly jump to the question, **Why we need data lake?** 
The answer is pretty broad, but I will try to explain in bullet points:

### Data movement
Data Lakes allow you to import any amount of data that can come in real-time. Data is collected from multiple sources, and moved into the data lake in its original format. This process allows you to scale to data of any size, while saving time of defining data structures, schema, and transformations.

### Analytics
Data Lakes allow various roles in your organization like data scientists, data developers, and business analysts to access data with their choice of analytic tools and frameworks. This includes open source frameworks such as Apache Hadoop, Presto, and Apache Spark, and commercial offerings from data warehouse and business intelligence vendors. Data Lakes allow you to run analytics without the need to move your data to a separate analytics system.

### Machine Learning
Data Lakes will allow organizations to generate different types of insights including reporting on historical data, and doing machine learning where models are built to forecast likely outcomes, and suggest a range of prescribed actions to achieve the optimal result.


## Here's a quick comparison table:

| Characteristics| Data Warehouse |Data Lake |
| :------ |:--- | :--- |
| Data | Designed prior to the DW implementation (schema-on-write) | 		Written at the time of analysis (schema-on-read)|
| Schema | 	Relational from transactional systems, operational databases, and line of business applications | 	Non-relational and relational from IoT devices, web sites, mobile apps, social media, and corporate applications|
| Data Quality | Highly curated data that serves as the central version of the truth | 	Any data that may or may not be curated (ie. raw data)|
| Analytics | Batch reporting, BI and visualizations | Machine Learning, Predictive analytics, data discovery and profiling |

**Courtsey: Amazon**

Thats all for now!
Hope you have a bit better understanding now :)

-Siddhartha Shrivastava
