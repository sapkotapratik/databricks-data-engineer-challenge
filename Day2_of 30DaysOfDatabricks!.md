
 Even though Data Lake is cost effective, provides scalability, and stores all types of data, but it does not provide
 ACID guarantees. 

So let's see what problems can occur.
 It's very important to understand this. 
Let's say you have a folder in Data Lake to store sales data, and two partition files are
 already stored there, part file 1 and part file 2. ![image](https://user-images.githubusercontent.com/24469318/212116352-2cebdb28-6b3d-4082-aee9-14d7cdb5a558.png)


![image](https://user-images.githubusercontent.com/24469318/212116452-86a31bd2-a29b-41e0-aa76-5fb6b5b3fc5a.png)


![image](https://user-images.githubusercontent.com/24469318/212116564-d7ccb407-b87c-49ee-b760-fb330a1f554b.png)


![image](https://user-images.githubusercontent.com/24469318/212116722-d7d3ef57-794e-416e-9995-ed7d8098ca72.png)


![image](https://user-images.githubusercontent.com/24469318/212116794-87c5d254-20f0-4967-aeeb-633dcad8af2b.png)




 So as you have seen, there are several challenges associated with Data Lake.
	-  It can have data reliability issues. If there is a job failure while writing, it may lead to data corruption, and you cannot even roll back the changes. 
	- No data validation is performed while writing, so a column could be written as an integer in one transaction and a string in another. And there can be consistency issues while reading the data.
	-  Also, if you have streaming data in your projects, it can be tough to handle along with batch data. 
	- Now one of the biggest drawbacks is that you cannot perform updates and deletes on files easily. And because of this, implementing GDPR, CCPA, or other compliances becomes a challenge. 
	- Then there can be data quality issues. As you saw, schema is not verified before writing the data. And unlike databases, you cannot apply checks on data. You have to handle all these things in your code. 
	- There can be query performance issues on Data Lake, which we'll be discussing later.
	-  And it's also difficult to maintain historical versions of data. 
	- So because of this, storing data in Data Lake becomes challenging. 
	- This is where Delta Lake comes in and can help us solve these challenges.
 But the question is, is Delta Lake the only option? No. 
There are other projects in the same space, like Apache Iceberg and Apache Hudi that works similarly to Delta Lake. Sounds good?

Even though data Lake is cost effective, provides scalability , and stores all types of data but is does not provide ACID gurantees.



So let's see what problem can occur 
It's very important to understand this.

Data Lake does NOT provide ACID guarantees



Challenges with Data Lake

Data reliability issues
	- Data corruption because of failures - no rollback!
	- No data validation
	- Consistency issues while reading data
Handling Batch and Streaming data together is tough
NO updates / deletes / merge on files
	- Difficult to implement GDPR / COPA compliance
Data quality issues
	- Schema isn't verified before writing
	- Cannot apply checks on data
Query performance issues
Difficult to maintain historical versions of data




Delta Lake can help us solve these challenges!




But is Delta Lake the only option?
Apache Iceberg
Apache Hudi


How Does Delta Lake Work?
Now that you have seen why Delta Lake is required, let's see how it works.
 -  Delta Lake is an open‑source storage layer that brings reliability to data lakes.
	-  Think of this like a small utility that you need to install on your Spark cluster. 
All right, so first let's see how to save the data in Parquet format. If you're not aware about Parquet, basically, it's a columnar format for files. Let's say you have created a DataFrame in Spark. Now when you save this DataFrame in parquet format, it will create and store multiple partition files in Parquet format. ![image](https://user-images.githubusercontent.com/24469318/212117048-2df3506b-b34f-4f16-8aa1-0d0ae861b354.png)
