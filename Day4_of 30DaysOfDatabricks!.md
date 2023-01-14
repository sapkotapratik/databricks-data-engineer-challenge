# Formula 1 Project

![image](https://user-images.githubusercontent.com/24469318/212461908-42b1f90d-6a5d-4020-a65b-132619c39a4d.png)

![image](https://user-images.githubusercontent.com/24469318/212461920-8b88d85a-041c-4ecb-b224-60227a269b07.png)

![image](https://user-images.githubusercontent.com/24469318/212461936-bc53f2c2-de94-44d2-b8ee-0b74ae4c872e.png)

![image](https://user-images.githubusercontent.com/24469318/212461941-d30c6883-7bf5-4e86-ae53-14ad0eb94d90.png)


![image](https://user-images.githubusercontent.com/24469318/212461971-5ae361dd-4213-42bc-b680-a57b74067fea.png)

![image](https://user-images.githubusercontent.com/24469318/212462029-84bbce7b-a0c6-4181-999a-50501673962d.png)

![image](https://user-images.githubusercontent.com/24469318/212462054-e49aefbd-916b-4a77-af81-9e67dbce90ab.png)

![image](https://user-images.githubusercontent.com/24469318/212462064-d7ed047b-d7c5-4ace-bf01-ef0e76b448f4.png)

![image](https://user-images.githubusercontent.com/24469318/212462078-80d5decf-aae4-449f-aff5-ddfe636be1aa.png)

![image](https://user-images.githubusercontent.com/24469318/212462089-522b2a9c-3ed5-4c1c-87d0-0df641de4d8d.png)


![image](https://user-images.githubusercontent.com/24469318/212462137-a3a96fa9-99f9-4972-8492-aa6443e3a1e5.png)


storage_account_name = "formula1dl"
client_id = "112d26f8--------------"
tenant_id = "--4b7c-4262-ae42-fbb379b1f18b"
client_secret = "-2w764dRlf1cV6"


configs = {"fs.azure.account.auth.type": "OAuth",
           "fs.azure.account.oauth.provider.type": "org.apache.hadoop.fs.azurebfs.oauth2.ClientCredsTokenProvider",
           "fs.azure.account.oauth2.client.id": f"{client_id}",
           "fs.azure.account.oauth2.client.secret": f"{client_secret}",
           "fs.azure.account.oauth2.client.endpoint": f"https://login.microsoftonline.com/{tenant_id}/oauth2/token"}
           

container_name = "raw"
dbutils.fs.mount(
  source = f"abfss://{container_name}@{storage_account_name}.dfs.core.windows.net/",
  mount_point = f"/mnt/{storage_account_name}/{container_name}",
  extra_configs = configs)
  
  dbutils.fs.ls("/mnt/formula1dlpratik/raw")
  
  ![image](https://user-images.githubusercontent.com/24469318/212462737-9b30223d-6a76-4c5d-a5f7-8bd44a34416a.png)
  
  
  dbutils.fs.mounts()
  
  
  
  def mount_adls(container_name):
  dbutils.fs.mount(
    source = f"abfss://{container_name}@{storage_account_name}.dfs.core.windows.net/",
    mount_point = f"/mnt/{storage_account_name}/{container_name}",
    extra_configs = configs)
  
  ![image](https://user-images.githubusercontent.com/24469318/212462790-9bacf609-3e13-4d81-81cb-ae280fc8aab2.png)
  
  mount_adls("processed")
  dbutils.fs.ls("/mnt/formula1dl/processed")
  
  
  ![image](https://user-images.githubusercontent.com/24469318/212462895-8d374fc4-953a-4fbc-9084-f636929d651c.png)


![image](https://user-images.githubusercontent.com/24469318/212462901-897d8758-1ab1-42fc-938c-180480d1ac7e.png)



Demo for working about using Key vault (Remaining)





















![image](https://user-images.githubusercontent.com/24469318/212459334-b61f7da0-0ab5-4204-b81f-651af3b2e94f.png)


![image](https://user-images.githubusercontent.com/24469318/212459345-16d66702-58b1-4bae-b10f-382492e50870.png)


![image](https://user-images.githubusercontent.com/24469318/212459366-2b637927-3ce5-4c49-a4fa-371e08f6c86a.png)


![image](https://user-images.githubusercontent.com/24469318/212459497-277d4c9e-23d3-466a-8d4d-8e849179f0da.png)

![image](https://user-images.githubusercontent.com/24469318/212459513-634c7b39-5a37-4ae1-b207-e5ceee91852b.png)

ergast.com/mrd/


![image](https://user-images.githubusercontent.com/24469318/212459550-d5a89dfe-08e0-4b2f-8f0d-7a374f5dbf36.png)

![image](https://user-images.githubusercontent.com/24469318/212459562-d0ed2fec-ea73-4f62-b7cd-9ed9548f1d30.png)


-- ER Diagram

![image](https://user-images.githubusercontent.com/24469318/212459588-40080e21-507b-4b3e-a9a3-142759f6ced3.png)

-- Database User guid (http://ergast.com/docs/f1db_user_guide.txt)
![image](https://user-images.githubusercontent.com/24469318/212466983-2ecc7ada-c4be-4afb-b9dc-ce66e9df2bd5.png)



![image](https://user-images.githubusercontent.com/24469318/212466991-64ac4e33-b393-4b17-8c16-275f9292a018.png)

![image](https://user-images.githubusercontent.com/24469318/212467002-ec0236f5-19ab-441d-9e2a-f4c296ec5a30.png)



![image](https://user-images.githubusercontent.com/24469318/212467009-38504949-7f5a-462d-8689-c92bd7078a69.png)
![image](https://user-images.githubusercontent.com/24469318/212467095-cc45f058-690a-4194-bb1e-4d44a4a02d18.png)





![image](https://user-images.githubusercontent.com/24469318/212467081-f084bbb4-f609-48d3-9d88-ed0414b67dc5.png)




![image](https://user-images.githubusercontent.com/24469318/212467057-a45961d2-f645-4b2c-98bb-3e5348777e62.png)



![image](https://user-images.githubusercontent.com/24469318/212467069-7fe71adc-3871-4c84-8b11-54ee6ea381ec.png)

![image](https://user-images.githubusercontent.com/24469318/212467041-2882d0f2-3c67-40b9-ab94-86f69d0130dd.png)



![image](https://user-images.githubusercontent.com/24469318/212467033-90729c2a-f695-4ea1-b1d5-0265285de98d.png)




![image](https://user-images.githubusercontent.com/24469318/212467023-66bc2635-efa9-49b7-a195-00958afdcb1c.png)

This work is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License
To view a copy of this license, visit: http://creativecommons.org/licenses/by-nc-sa/3.0/

Out of 12 files based on List we are going to work on 8 files only.


![image](https://user-images.githubusercontent.com/24469318/212459785-b993d934-7fb6-4a05-80fa-a7ce20e48d24.png)


![image](https://user-images.githubusercontent.com/24469318/212459833-321c81ad-b1b5-421b-9647-83e3e4cbbda4.png)


![image](https://user-images.githubusercontent.com/24469318/212459903-6475324c-7e27-4ea7-bbed-2d9e9fbbc0f7.png)


![image](https://user-images.githubusercontent.com/24469318/212459924-ee5b7814-aff2-403f-a008-3b4e8152f111.png)


![image](https://user-images.githubusercontent.com/24469318/212459941-0361dd2e-3646-411a-9e31-e5cc7f191480.png)


![image](https://user-images.githubusercontent.com/24469318/212459953-a65684ed-563d-4fed-af80-8db5a8d8d6cd.png)


![image](https://user-images.githubusercontent.com/24469318/212459966-f09eaa68-5308-421e-8748-35fd176f6658.png)

![image](https://user-images.githubusercontent.com/24469318/212459981-e926db3d-47b6-46e4-86f8-29b7944e4fc8.png)


![image](https://user-images.githubusercontent.com/24469318/212459992-ab4d4616-4613-42e4-975e-6f1e516c658d.png)

![image](https://user-images.githubusercontent.com/24469318/212460045-77a7c8cf-031d-45c1-bcfc-6067c1d6195c.png)

(https://learn.microsoft.com/en-us/azure/architecture/solution-ideas/articles/azure-databricks-modern-analytics-architecture)
![image](https://user-images.githubusercontent.com/24469318/212460092-4c620c2c-83f5-4858-b95c-0c4d639a357b.png)

https://learn.microsoft.com/en-us/azure/architecture/solution-ideas/articles/azure-databricks-modern-analytics-architecture


![image](https://user-images.githubusercontent.com/24469318/212460177-1ba2d517-fddf-4bf7-bbee-577477c81afb.png)



https://learn.microsoft.com/en-us/azure/architecture/

For Databricks:

https://learn.microsoft.com/en-us/azure/architecture/browse/?terms=azure%20databricks

![image](https://user-images.githubusercontent.com/24469318/212460800-aa2b8e25-468f-4059-8659-dd52fcf5f18f.png)

![image](https://user-images.githubusercontent.com/24469318/212460809-cfadbb6a-9d77-4dc1-b337-0ef6f1982cfe.png)

![image](https://user-images.githubusercontent.com/24469318/212460818-5d60ac6e-f6e0-45d3-8bd6-81326bf7d581.png)


![image](https://user-images.githubusercontent.com/24469318/212460827-8304e631-c8aa-4345-9205-9a01ee38eadf.png)


![image](https://user-images.githubusercontent.com/24469318/212460839-783357c4-ac4f-43df-90f6-61dbbfebd4f5.png)



![image](https://user-images.githubusercontent.com/24469318/212461047-d0b40072-7516-4362-8fe0-c7e21a53f045.png)

- Spark does it's big data processing by breaking down the applicationinto many smaller jobs, stages and tasks to parallelize the work.
- One of the key constructs behind these are spot data frames.
-  Dataframes can be represented as row and columns with defined data types.
-  Each data frame is then divided into logical partitions, which could then be computed by different executor or slots as we have seen previously.
-  This gives spark the ability to divide the work and create smaller tasks and execute them in parallel to get the results quickly for our project.

![image](https://user-images.githubusercontent.com/24469318/212461278-43673a1f-0329-4432-9e5d-a68cc441b0c2.png)

![image](https://user-images.githubusercontent.com/24469318/212461355-8175b37b-c7b7-4f92-95b6-026782324f03.png)

![image](https://user-images.githubusercontent.com/24469318/212461405-09347f65-c173-4b0d-8126-63dd840942f9.png)


![image](https://user-images.githubusercontent.com/24469318/212461433-b817ca35-7c22-412b-b146-befdde05b5e7.png)


![image](https://user-images.githubusercontent.com/24469318/212461451-62dea5ef-61ba-4a1f-865e-95d8eb243e40.png)

![image](https://user-images.githubusercontent.com/24469318/212461551-04eebce0-e222-4aa4-a7d0-e9671dff3214.png)

https://spark.apache.org/docs/latest/api/python/reference/index.html



![image](https://user-images.githubusercontent.com/24469318/212463551-53d5ab7c-2116-422f-bab0-494fbb8697c2.png)

![image](https://user-images.githubusercontent.com/24469318/212463573-996e767f-162b-4ce8-896e-3fb662281b10.png)

- When inferSchema is true spark is going through the data and reading all of the data and identify what schema is and apply that schema to the dataframe which is not efficient since it has to read through the data.

- In the prod there would a lot of data and it slow down your reads.


- And also, if you get data which doesn't conform to what you're expecting, you want process to fail and tell you that there is sth wrong rathe than just infering the schema and carrying on.

https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/data_types.html

Struct type represents your row.

StructFields represents your column

![image](https://user-images.githubusercontent.com/24469318/212464519-820f8a25-9364-4959-ab86-7bbba23e1d0a.png)


![image](https://user-images.githubusercontent.com/24469318/212464549-fe8d4058-ba2c-4b4b-a18f-6d6b5f785094.png)


![image](https://user-images.githubusercontent.com/24469318/212464778-efeb2123-42b6-4ed8-a086-81412512d562.png)



- This way of selecting columns allow you to make column based function for eg. if you wanted to change the name of the column , you can do it here.


![image](https://user-images.githubusercontent.com/24469318/212465026-8432ceeb-2c54-4114-923a-8674bdcb9c2d.png)


![image](https://user-images.githubusercontent.com/24469318/212465526-1fd744de-118a-4592-85e9-2c636375169f.png)


![image](https://user-images.githubusercontent.com/24469318/212465538-88b5843d-96b8-42f4-a799-18358aa192eb.png)

![image](https://user-images.githubusercontent.com/24469318/212465654-85929f8c-4b66-406e-8a8d-0c73141cf41c.png)


![image](https://user-images.githubusercontent.com/24469318/212465883-b12dd0ec-ee31-447f-bfd5-bb7d3e678ab5.png)


Here data is in single partition. We can make it to multiple partitions as well.


![image](https://user-images.githubusercontent.com/24469318/212466141-17f002ac-92e7-4ff7-8e99-845c99403449.png)







