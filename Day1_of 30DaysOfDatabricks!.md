# Delta Lake

![image](https://user-images.githubusercontent.com/24469318/211700605-450cc3d5-28a7-4a0f-bfa7-43d0ac37ef66.png)

![image](https://user-images.githubusercontent.com/24469318/211700622-e166f9ad-4e39-47ac-ae5b-be72b17b5ec0.png)


![image](https://user-images.githubusercontent.com/24469318/211700647-b371a02b-111c-46a0-90f2-6a00e5e9aead.png)

![image](https://user-images.githubusercontent.com/24469318/211700669-63547e30-ff1c-4b4a-a99f-ffc090ace67e.png)

![image](https://user-images.githubusercontent.com/24469318/211700818-852d4f3f-3522-45a5-aebd-7c724f6aa671.png)


![image](https://user-images.githubusercontent.com/24469318/211700905-7c619dc3-ff35-4c52-a1b1-f44d5e501ac1.png)

![image](https://user-images.githubusercontent.com/24469318/211701001-0d24b470-bae1-48a6-a735-642dfdec0e2d.png)

![image](https://user-images.githubusercontent.com/24469318/211701525-8f588eda-72a3-4fca-9cfd-07835f4af678.png)



- Note that Databricks doesn't have a **COMMIT** keyword; transactions run as soon as they're executed, and commit as they succeed.


- What may surprise you is that Delta Lake guarantees that any read against a table will always return the most recent version of the table, and that 
<br> you'll never encounter a state of deadlock due to ongoing operations.

- To repeat: table reads can never conflict with other operations, and the newest version of your data is immediately <br>
 available to all clients that can query your lakehouse. Because all transaction information is stored in cloud object<br>
 storage alongside your data files, concurrent reads on Delta Lake tables is limited only by the hard limits of object storage on cloud vendors. 
 
- (NOTE: It's not infinite, but it's at least thousands of reads per second.)


**Updating records** provides atomic guarantees as well: we perform a snapshot read of the current version of our table, find all fields 
<br> that match our WHERE clause, and then apply the changes as described.

- Below, we find all students that have a name starting with the letter **T** and add 1 to the number in their **`value`** column.

![image](https://user-images.githubusercontent.com/24469318/211703388-11f280ac-d1b8-496c-801a-36a200c0ebb5.png)


## Deleting Records

Deletes are also atomic, so there's no risk of only partially succeeding when removing data from your data lakehouse.

- A **`DELETE`** statement can remove one or many records, but will always result in a single transaction.


![image](https://user-images.githubusercontent.com/24469318/211703661-df20cdf6-3ee1-41e1-9dcb-0a1498abe17f.png)


![image](https://user-images.githubusercontent.com/24469318/211706446-dc7fd1a5-f97e-402d-9485-197461707fc2.png)


![image](https://user-images.githubusercontent.com/24469318/211706575-d736d765-a869-43a1-b09e-fca34702d620.png)

![image](https://user-images.githubusercontent.com/24469318/211707562-72ed131b-41c8-435c-b51d-376c419dde75.png)



![image](https://user-images.githubusercontent.com/24469318/211708726-7196f563-1edb-45d1-9d68-e44017a78ce6.png)


![image](https://user-images.githubusercontent.com/24469318/211708844-c075b66c-576f-4e45-ba57-79cdb652e9d6.png)


![image](https://user-images.githubusercontent.com/24469318/211708980-461e41e8-50f9-4817-b97a-462d154ff671.png)


![image](https://user-images.githubusercontent.com/24469318/211709396-097ffc9a-c05b-4645-9881-d82702fcba43.png)


![image](https://user-images.githubusercontent.com/24469318/211709452-ed74c560-4661-4738-af1b-00ffc8b50609.png)


![image](https://user-images.githubusercontent.com/24469318/211709501-eca3b0bb-3c58-4fb7-b37c-c32e31358f39.png)


![image](https://user-images.githubusercontent.com/24469318/211709653-7b589ff7-4161-49c0-b45e-70442606527f.png)


![image](https://user-images.githubusercontent.com/24469318/211709740-9a67a8a2-7199-4969-bae7-406e77321f5c.png)


![image](https://user-images.githubusercontent.com/24469318/211710059-127dbe5f-2b8e-403a-8adf-040528c8c8e3.png)


![image](https://user-images.githubusercontent.com/24469318/211710308-a7867d1f-525a-4e61-8812-ea359fbbee2e.png)
















* The ONLY PySpark Tutorial You Will Ever Need *

https://www.youtube.com/watch?v=cZS5xYYIPzk

![image](https://user-images.githubusercontent.com/24469318/211714135-c7257ad1-6d13-4661-baeb-f1abd4d51233.png)

- Spark is a system design for  working ,analyzing and modelling with immense amounts of data in many computers at same time putting it in a different way.

- Spark allows you to run computations in parallel instead of sequentially it allows you to divide one incredibly large task into many smaller tasks and run 
 each such task on a different machine.
 
- By this you can accomplish your analysis goals in a reasonable time that would not be possible on a single machine

- Pyspark is just a python API for working with spark.
-
- ![image](https://user-images.githubusercontent.com/24469318/211717512-730b4408-e051-4937-8a8e-5623a3d98ecb.png)


- And what I mean by a python api is that you can use the syntax and agility of the familiar python to interact and send commands to a system that is not based
at its core on python

![image](https://user-images.githubusercontent.com/24469318/211717441-0d47b5e4-fd76-4737-aa35-337ecc53da69.png)
- Usually we would define this amount that suits using Pyspark is the amout that would not fit into single machine's storage 

 
![image](https://user-images.githubusercontent.com/24469318/211717730-20dfddf6-c583-4f63-a31f-19359a67355c.png)

when you distribute a task into several smaller tasks that run at the same time with many machines, this is what Pyspark allows you to do but it can be 
done on a single machine with several threads. 

![image](https://user-images.githubusercontent.com/24469318/211718161-5766a31b-8b16-482d-9dad-374b3fe7d347.png)


For example a cluster is a n/w of machines that can take on tasks from a user , interact with one another and return results.

This provide the computing resources that Pyspark will use to make the computations 


![image](https://user-images.githubusercontent.com/24469318/211718357-50c981e2-e4a5-4dc1-a150-830d2ddbad59.png)

RDD is one of the kinds of data setsthat pi spark is using

- It's an immutable distributed collection of data which is not tabular like spark data frames which which we will be working with later and it has no data schema.
- It means it has no defined data types.


- Therefore for tabular data wrangling spark data frames allows for more API options and better under the hood optimization.

- Still you might encounter Rdds as you learn more about spark and you should be aware of their existence 

![image](https://user-images.githubusercontent.com/24469318/211719444-ef0eb3e3-da5c-40cd-8160-014b70d10446.png)

- out of the four main parts of pi spark we are going to cover 2.
- we are going to cover Pypark sql which contains commands for data processing and manipulation and a bit of  Pyspark ml lib which includes a variety of machine learning models and
model training related commands we want however covergraphics which is used for working withgraphs and the streaming package thatdeals with analyzing and processing data
that is collected real time from various sources at once.

![image](https://user-images.githubusercontent.com/24469318/211719687-5355e17a-2d0a-4716-86bc-1fc5d887c12c.png)


- now let me briefly explain the basics of the spark architecture to send commands and receive results from a cluster you will need to initiate a spark session s
- this object is your tool for interacting with spark each user of the cluster willhave its own spark session that willallow him to use the cluster in
isolation from other users
- spark session communicates with sparks context which is the master node in the cluster that is it assigns each comp of thecomputers in the cluster tasks and
coordinates them each of the computers in the cluster that performs tasks for a master node is called a worker node to connect to a worker node the master
nodes needed to get that worker node's computing power allocated to it by a cluster manager that is responsible for distributing thecluster's resources

- inside each worker node there are executable programs that run the tasks. they can run multiple tasks simultaneously and has their own cache for storing results
- so each master node can have multiple worker nodes that can have multiple tasks running 

![image](https://user-images.githubusercontent.com/24469318/211720233-07a7e6d6-999b-469c-ac10-3cb191251b5c.png)


- to initiate a spark session by which we will perform analysis first import it from the spark sql
- if you don't have this library installed just pip install pyspark
- then we use the spark session.builder command giving our session a name and applying get or create
- it will create a session for you or retrieve existing one if it exists in your workspace

![image](https://user-images.githubusercontent.com/24469318/211720371-cfba6185-0271-44a2-927c-cceb35a59ab4.png)


- To see some info about your session just type spark in your notebook you will be able to see the version that you are using
information about the cluster .

![image](https://user-images.githubusercontent.com/24469318/211720442-27206748-f81d-427e-8bc2-c34a477122ae.png)

- here i run pyspark locally on my pc and the asterix symbol indicates that spark is using allof my machine cores
and the name of the session


- to load the csv use the spark read command and set header to true  if the first line in the csv contains the column names

- note that all of the columns will be of data type string if you want to tell Pyspark the column name the column types use a
schema string that specifies them for each column and pass it as an argument to the function.

![image](https://user-images.githubusercontent.com/24469318/211720809-6070ff86-3338-462f-a25f-7c4b85541ed1.png)


- here i also show an equivalent way to set header to true.to get pyspark to infer the column data types by itself use infer schema

![image](https://user-images.githubusercontent.com/24469318/211721043-fa27a8be-cc2d-4571-befa-c920edec71b7.png)


- And if you want to replace null values with another value upon loading use the null value argument
- If u want to save a file use the write ommand and specify the file format and ath to saving but that won't let you overwrite  existing file.
- to do that you needed to set the modeto overwrite

![image](https://user-images.githubusercontent.com/24469318/211721379-61dc5d09-220e-4551-abce-f71f85e5af59.png)

-use the dot count to count the number of rows in your dataframe

![image](https://user-images.githubusercontent.com/24469318/211721477-13c14020-84f2-4f36-b0c3-4646f461697d.png)



- and to show the first few rows of the table use the show command and you will get the rows as output

![image](https://user-images.githubusercontent.com/24469318/211721585-ab557579-3e7e-40c1-8150-c44a455399c1.png)

- but if you just want to see a column or two use the select command with a column name or with a list of column names


![image](https://user-images.githubusercontent.com/24469318/211721761-c86b7d41-c7c8-4233-9849-2fbfcc4ca811.png)

- okay back to some basic theory pandas data frame versus pyspark  dataframe

![image](https://user-images.githubusercontent.com/24469318/211721865-56533d8a-cd8a-4429-8811-7cb525fed448.png)

- both represent a table of data with rows and columns and schema however under the hood they are different as pi spark data frames needs to support the distributed computations 
as we move forward we will see more and more features of it that are not present in pandas data frame.that being said if you know how to usepandas then moving to pi spark will feel
like a natural transition .

- directed acyclic graphs or dags a directed acyclic graph is the way spark runs computations when you give it a series of transformations to apply to a data set it builds a graph out of 
those transformations so it knows what to do but it does not execute those commands  
immediately if it doesn't have to rather it is lazy it will go through the dag and apply transformations only when it must to provide a needed result this allows better performance since 
spark knows what's ahead of a certain computation and can and can get optimizing the process accordingly.


![image](https://user-images.githubusercontent.com/24469318/211722168-71fac5bd-3435-4962-9192-d9d86dfbf5b8.png)

- note that as you transform the data a new data frame object is created you do not write over the previous one 

![image](https://user-images.githubusercontent.com/24469318/211722527-9d86c38b-484a-4190-a167-b5a54c1763c3.png)


- in pi spark there are two types of commands transformations and actions transformations commands are added to the dag but does not get to be actually 
executed until an action is called they only transform one data frame into another not changing the input data frame 
- actions on the other hand make pi spark 
execute the dag but does not create a new data frame instead they output the 
result of the dag to you the user 

- every time you run a dag it will be recomputed from the beginning that is the results are not saved in 
memory so if you want to save the result so it wants to be re it won't have to be 
recomputed we can use the cache command note that this will occupy space in the working 
nodes memory so be careful with the sizes of data sets you are caching 


![image](https://user-images.githubusercontent.com/24469318/211723038-c7470566-c16e-45a0-95f8-685deb1b502a.png)


- by default the cached data frame is stored to RAM and is unserialized that is not converted into a stream of bytes 

- you can change both of these store data to hard drive and serialize it or both 
even after caching it out of frame it still sits in the worker node's memory 

- if you want to collect its pieces assemble them and save them on the 
master node so you won't have to pull it every single time use the command for 
collecting 
again be very careful with this since 
the collected file will have to fit in 
the master node's memory you will rarely 
use this command explicitly but it is 
integrated into many other common 
commands that involve inspecting the 
data such as the show command we have 
seen 
to convert a pi spark data frame into a 
pandas data frame use the two pandas 
commander to convert it back into a pi 
spark data frame use the create data 
frame command 
to see column data types and whether 
they accept null values use the print 
schema command 
or use dot d types to get the data types 
as a list of tuples 
to cast a column into a different data 
type 
import the data type you need and use
the width column command that allows you
to apply a transformation to a column
combined with the cast command
to remove a column use the drop command
and to rename it use the with column
renamed command
to rename several columns defined a
tuple with the old and new column names
loop over the tuples and change them
individually
to get summary statistics about your
data
first pick the columns of interest
use the describe command
and show the results
you will get a table of statistics like
count average and more
to deal with null values in your data
set you can simply drop all rows that
contain a single null value
draw rows that has nothing but null
values
order pros with more than certain number
of values that are not null
you can also drop null values
considering only a subset of columns
and replace null values with a different
value
to replace nulls in a less crude way use
spark's computer object
initiate it with the columns you want to
fill nulls in as both input and output
columns
and set a replacing strategy such as the
mean of the column but it can also be
set to median and other values as well
then fit the imputer to the data and
transform
to filter based on the condition just
use the filter command with a string
that contains the column to filter by
and the condition
the where command is just an alias for
the filter command and yields the same
results
and instead of a string you can insert a
column and apply a condition this syntax
is
great for applying multiple conditions
using the end operator or the or
operator
use the tilde sign to pick all of the
rows that don't meet the specified
condition
sometimes it's useful to write a command
as a string to do that import the x bar
command
and type the expression you want spark
to evaluate for example some
mathematical combination of two columns
then use the expire command in
combination with the with column command
to apply the expression to a column of
your choice
the group by command allows you to
divide your data into groups based on
some value
age for example
and calculate a statistic for each group
then pick the column you care about the
column of the statistic
and show
them you will get a result
to sort the result
import the desk command for descending
order or the ask for ascending order
save the result of the group by into a
variable
and order them like this
to calculate several statistics import
the function sub module
and apply the functions you need
with the aggregation command
you can combine this grouping to get
stats for each group
if you are feeling more comfortable with
an sql syntax you can use that
instead
by telling spark how your table is
called
and typing in your query
we can also choose columns using sql
syntax with a command that combines the
dot select command and the dot sql
command
if you have two columns for example
agent sex and you want to know more
about the way they interact pivot table
is a great option for example to get the
counts for each combination of agent
effects
use df
dot group by age
dot pivot sex dot count
note that pivoting is an expensive
operation computationally but you can
make it cheaper by providing the pivot
function the values you want to pivot on
you can combine the commands we have
seen in many ways to create more
complicated expressions for example
by creating a column of true and false
for where an age is above a certain
value using the select expression
command
grouping by another value
and pivoting on the boolean column we
created which will give you a summary of
the distribution of ages within each
gender
to divide the dataset into train and
test set
simply use the random split command
with the division proportion of interest
to do machine learning with pi spark
it's important to know that pi spark
won't accept a table of feature columns
but instead it requires a single column
where each entry is a vector of the
feature columns
so each row in the column is a vector
and each value in the vector is a
different feature such as age and six
to create this vector first define your
feature columns and then import the
vector assembler object
and initiate it
start state stating the feature column
names
and the name of the new column with the
vector feature
and apply the vector assembler to the
data to transform it
to use a machine learning model with pi
spark start by importing it
then initiate it
stating the feature vector column and
the target column which you like to
predict
fit the model to the data so it can
learn from it
and check any attributes of interest
now you can use it to make predictions
this is it guys i hope you enjoyed this
crash course on pi spark
there are always more to learn but now
you are ready to take an interesting
data set and get your hands dirty with
pispar code if you want to see more
about pi spark
-fr example maybe a example analysis let
me know in the comments
and if you want to be notified when a
new data science video is coming out
remember to subscribe



