# Formula 1 Project

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

+----------------------------+
| Ergast Database User Guide |
+----------------------------+
| Version: 1.0               |
| Date: 31 January 2021      |
| Author: Chris Newell       |
+----------------------------+

+----------------------+          +------------------------------------------------------------------+
| List of Tables       |          | General Notes                                                    |
+----------------------+          +------------------------------------------------------------------|
| circuits             |          | Dates, times and durations are in ISO 8601 format                |
| constructorResults   |          | Dates and times are UTC                                          |
| constructorStandings |          | Strings use UTF-8 encoding                                       |
| constructors         |          | Primary keys are for internal use only                           |
| driverStandings      |          | Fields ending with "Ref" are unique identifiers for external use |
| drivers              |          | A grid position of '0' is used for starting from the pitlane     |
| lapTimes             |          | Labels used in the positionText fields:                          |
| pitStops             |          |   "D" - disqualified                                             |
| qualifying           |          |   "E" - excluded                                                 |
| races                |          |   "F" - failed to qualify                                        |
| results              |          |   "N" - not classified                                           |
| seasons              |          |   "R" - retired                                                  |
| status               |          |   "W" - withdrew                                                 |
+----------------------+          +------------------------------------------------------------------+

circuits table
+------------+--------------+------+-----+---------+----------------+---------------------------+
| Field      | Type         | Null | Key | Default | Extra          | Description               |
+------------+--------------+------+-----+---------+----------------+---------------------------+
| circuitId  | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key               |
| circuitRef | varchar(255) | NO   |     |         |                | Unique circuit identifier |
| name       | varchar(255) | NO   |     |         |                | Circuit name              |
| location   | varchar(255) | YES  |     | NULL    |                | Location name             |
| country    | varchar(255) | YES  |     | NULL    |                | Country name              |
| lat        | float        | YES  |     | NULL    |                | Latitude                  |
| lng        | float        | YES  |     | NULL    |                | Longitude                 |
| alt        | int(11)      | YES  |     | NULL    |                | Altitude (metres)         |
| url        | varchar(255) | NO   | UNI |         |                | Circuit Wikipedia page    |
+------------+--------------+------+-----+---------+----------------+---------------------------+

constructor_results table
+----------------------+--------------+------+-----+---------+----------------+----------------------------------------+
| Field                | Type         | Null | Key | Default | Extra          | Description                            |
+----------------------+--------------+------+-----+---------+----------------+----------------------------------------+
| constructorResultsId | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                            |
| raceId               | int(11)      | NO   |     | 0       |                | Foreign key link to races table        |
| constructorId        | int(11)      | NO   |     | 0       |                | Foreign key link to constructors table |
| points               | float        | YES  |     | NULL    |                | Constructor points for race            |
| status               | varchar(255) | YES  |     | NULL    |                | "D" for disqualified (or null)         |
+----------------------+--------------+------+-----+---------+----------------+----------------------------------------+

constructor_standings table
+------------------------+--------------+------+-----+---------+----------------+------------------------------------------+
| Field                  | Type         | Null | Key | Default | Extra          | Description                              |
+------------------------+--------------+------+-----+---------+----------------+------------------------------------------+
| constructorStandingsId | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                              |
| raceId                 | int(11)      | NO   |     | 0       |                | Foreign key link to races table          |
| constructorId          | int(11)      | NO   |     | 0       |                | Foreign key link to constructors table   |
| points                 | float        | NO   |     | 0       |                | Constructor points for season            |
| position               | int(11)      | YES  |     | NULL    |                | Constructor standings position (integer) |
| positionText           | varchar(255) | YES  |     | NULL    |                | Constructor standings position (string)  |
| wins                   | int(11)      | NO   |     | 0       |                | Season win count                         |
+------------------------+--------------+------+-----+---------+----------------+------------------------------------------+

constructors table
+----------------+--------------+------+-----+---------+----------------+-------------------------------+
| Field          | Type         | Null | Key | Default | Extra          | Description                   |
+----------------+--------------+------+-----+---------+----------------+-------------------------------+
| constructorId  | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                   |
| constructorRef | varchar(255) | NO   |     |         |                | Unique constructor identifier |
| name           | varchar(255) | NO   | UNI |         |                | Constructor name              |
| nationality    | varchar(255) | YES  |     | NULL    |                | Constructor nationality       |
| url            | varchar(255) | NO   |     |         |                | Constructor Wikipedia page    |
+----------------+--------------+------+-----+---------+----------------+-------------------------------+

driver_standings table
+-------------------+--------------+------+-----+---------+----------------+-------------------------------------+
| Field             | Type         | Null | Key | Default | Extra          | Description                         |
+-------------------+--------------+------+-----+---------+----------------+-------------------------------------+
| driverStandingsId | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                         |
| raceId            | int(11)      | NO   |     | 0       |                | Foreign key link to races table     |
| driverId          | int(11)      | NO   |     | 0       |                | Foreign key link to drivers table   |
| points            | float        | NO   |     | 0       |                | Driver points for season            |
| position          | int(11)      | YES  |     | NULL    |                | Driver standings position (integer) |
| positionText      | varchar(255) | YES  |     | NULL    |                | Driver standings position (string)  |
| wins              | int(11)      | NO   |     | 0       |                | Season win count                    |
+-------------------+--------------+------+-----+---------+----------------+-------------------------------------+

drivers table
+-------------+--------------+------+-----+---------+----------------+--------------------------+
| Field       | Type         | Null | Key | Default | Extra          | Description              |
+-------------+--------------+------+-----+---------+----------------+--------------------------+
| driverId    | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key              |
| driverRef   | varchar(255) | NO   |     |         |                | Unique driver identifier |
| number      | int(11)      | YES  |     | NULL    |                | Permanent driver number  |
| code        | varchar(3)   | YES  |     | NULL    |                | Driver code e.g. "ALO"   |     
| forename    | varchar(255) | NO   |     |         |                | Driver forename          |
| surname     | varchar(255) | NO   |     |         |                | Driver surname           |
| dob         | date         | YES  |     | NULL    |                | Driver date of birth     |
| nationality | varchar(255) | YES  |     | NULL    |                | Driver nationality       |
| url         | varchar(255) | NO   | UNI |         |                | Driver Wikipedia page    |
+-------------+--------------+------+-----+---------+----------------+--------------------------+

lap_times table
+--------------+--------------+------+-----+---------+-------+-----------------------------------+
| Field        | Type         | Null | Key | Default | Extra | Description                       |
+--------------+--------------+------+-----+---------+-------+-----------------------------------+
| raceId       | int(11)      | NO   | PRI | NULL    |       | Foreign key link to races table   |
| driverId     | int(11)      | NO   | PRI | NULL    |       | Foreign key link to drivers table |
| lap          | int(11)      | NO   | PRI | NULL    |       | Lap number                        |
| position     | int(11)      | YES  |     | NULL    |       | Driver race position              |
| time         | varchar(255) | YES  |     | NULL    |       | Lap time e.g. "1:43.762"          |
| milliseconds | int(11)      | YES  |     | NULL    |       | Lap time in milliseconds          |
+--------------+--------------+------+-----+---------+-------+-----------------------------------+

pit_stops table
+--------------+--------------+------+-----+---------+-------+-----------------------------------+
| Field        | Type         | Null | Key | Default | Extra | Description                       |
+--------------+--------------+------+-----+---------+-------+-----------------------------------+
| raceId       | int(11)      | NO   | PRI | NULL    |       | Foreign key link to races table   |
| driverId     | int(11)      | NO   | PRI | NULL    |       | Foreign key link to drivers table |
| stop         | int(11)      | NO   | PRI | NULL    |       | Stop number                       |
| lap          | int(11)      | NO   |     | NULL    |       | Lap number                        |
| time         | time         | NO   |     | NULL    |       | Time of stop e.g. "13:52:25"      |
| duration     | varchar(255) | YES  |     | NULL    |       | Duration of stop e.g. "21.783"    |
| milliseconds | int(11)      | YES  |     | NULL    |       | Duration of stop in milliseconds  |
+--------------+--------------+------+-----+---------+-------+-----------------------------------+

qualifying table
+---------------+--------------+------+-----+---------+----------------+----------------------------------------+
| Field         | Type         | Null | Key | Default | Extra          | Description                            |
+---------------+--------------+------+-----+---------+----------------+----------------------------------------+
| qualifyId     | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                            |
| raceId        | int(11)      | NO   |     | 0       |                | Foreign key link to races table        |
| driverId      | int(11)      | NO   |     | 0       |                | Foreign key link to drivers table      |
| constructorId | int(11)      | NO   |     | 0       |                | Foreign key link to constructors table |
| number        | int(11)      | NO   |     | 0       |                | Driver number                          |
| position      | int(11)      | YES  |     | NULL    |                | Qualifying position                    |
| q1            | varchar(255) | YES  |     | NULL    |                | Q1 lap time e.g. "1:21.374"            |
| q2            | varchar(255) | YES  |     | NULL    |                | Q2 lap time                            |
| q3            | varchar(255) | YES  |     | NULL    |                | Q3 lap time                            |
+---------------+--------------+------+-----+---------+----------------+----------------------------------------+

races table
+-------------+--------------+------+-----+------------+----------------+------------------------------------+
| Field       | Type         | Null | Key | Default    | Extra          | Description                        |
+-------------+--------------+------+-----+------------+----------------+------------------------------------+
| raceId      | int(11)      | NO   | PRI | NULL       | auto_increment | Primary key                        |
| year        | int(11)      | NO   |     | 0          |                | Foreign key link to seasons table  |
| round       | int(11)      | NO   |     | 0          |                | Round number                       |
| circuitId   | int(11)      | NO   |     | 0          |                | Foreign key link to circuits table |
| name        | varchar(255) | NO   |     |            |                | Race name                          | 
| date        | date         | NO   |     | 0000-00-00 |                | Race date e.g. "1950-05-13"        |
| time        | time         | YES  |     | NULL       |                | Race start time e.g."13:00:00"     |
| url         | varchar(255) | YES  | UNI | NULL       |                | Race Wikipedia page                |
| fp1_date    | date         | YES  |     | NULL       |                | FP1 date                           |
| fp1_time    | time         | YES  |     | NULL       |                | FP1 start time                     |
| fp2_date    | date         | YES  |     | NULL       |                | FP2 date                           |
| fp2_time    | time         | YES  |     | NULL       |                | FP2 start time                     |
| fp3_date    | date         | YES  |     | NULL       |                | FP3 date                           |
| fp3_time    | time         | YES  |     | NULL       |                | FP3 start time                     |
| quali_date  | date         | YES  |     | NULL       |                | Qualifying date                    |
| quali_time  | time         | YES  |     | NULL       |                | Qualifying start time              |
| sprint_date | date         | YES  |     | NULL       |                | Sprint date                        |
| sprint_time | time         | YES  |     | NULL       |                | Sprint start time                  |
+-------------+--------------+------+-----+------------+----------------+------------------------------------+

results table
+-----------------+--------------+------+-----+---------+----------------+---------------------------------------------+
| Field           | Type         | Null | Key | Default | Extra          | Description                                 |
+-----------------+--------------+------+-----+---------+----------------+---------------------------------------------+
| resultId        | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                                 |
| raceId          | int(11)      | NO   |     | 0       |                | Foreign key link to races table             |
| driverId        | int(11)      | NO   |     | 0       |                | Foreign key link to drivers table           |
| constructorId   | int(11)      | NO   |     | 0       |                | Foreign key link to constructors table      |
| number          | int(11)      | YES  |     | NULL    |                | Driver number                               |
| grid            | int(11)      | NO   |     | 0       |                | Starting grid position                      |
| position        | int(11)      | YES  |     | NULL    |                | Official classification, if applicable      |
| positionText    | varchar(255) | NO   |     |         |                | Driver position string e.g. "1" or "R"      |
| positionOrder   | int(11)      | NO   |     | 0       |                | Driver position for ordering purposes       |
| points          | float        | NO   |     | 0       |                | Driver points for race                      |
| laps            | int(11)      | NO   |     | 0       |                | Number of completed laps                    |
| time            | varchar(255) | YES  |     | NULL    |                | Finishing time or gap                       |
| milliseconds    | int(11)      | YES  |     | NULL    |                | Finishing time in milliseconds              |   
| fastestLap      | int(11)      | YES  |     | NULL    |                | Lap number of fastest lap                   |
| rank            | int(11)      | YES  |     | 0       |                | Fastest lap rank, compared to other drivers |
| fastestLapTime  | varchar(255) | YES  |     | NULL    |                | Fastest lap time e.g. "1:27.453"            |
| fastestLapSpeed | varchar(255) | YES  |     | NULL    |                | Fastest lap speed (km/h) e.g. "213.874"     |
| statusId        | int(11)      | NO   |     | 0       |                | Foreign key link to status table            |
+-----------------+--------------+------+-----+---------+----------------+---------------------------------------------+

sprint_results table
+-----------------+--------------+------+-----+---------+----------------+---------------------------------------------+
| Field           | Type         | Null | Key | Default | Extra          | Description                                 |
+-----------------+--------------+------+-----+---------+----------------+---------------------------------------------+
| sprintResultId  | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                                 |
| raceId          | int(11)      | NO   |     | 0       |                | Foreign key link to races table             |
| driverId        | int(11)      | NO   |     | 0       |                | Foreign key link to drivers table           |
| constructorId   | int(11)      | NO   |     | 0       |                | Foreign key link to constructors table      |
| number          | int(11)      | YES  |     | NULL    |                | Driver number                               |
| grid            | int(11)      | NO   |     | 0       |                | Starting grid position                      |
| position        | int(11)      | YES  |     | NULL    |                | Official classification, if applicable      |
| positionText    | varchar(255) | NO   |     |         |                | Driver position string e.g. "1" or "R"      |
| positionOrder   | int(11)      | NO   |     | 0       |                | Driver position for ordering purposes       |
| points          | float        | NO   |     | 0       |                | Driver points for race                      |
| laps            | int(11)      | NO   |     | 0       |                | Number of completed laps                    |
| time            | varchar(255) | YES  |     | NULL    |                | Finishing time or gap                       |
| milliseconds    | int(11)      | YES  |     | NULL    |                | Finishing time in milliseconds              |   
| fastestLap      | int(11)      | YES  |     | NULL    |                | Lap number of fastest lap                   |
| fastestLapTime  | varchar(255) | YES  |     | NULL    |                | Fastest lap time e.g. "1:27.453"            |
| statusId        | int(11)      | NO   |     | 0       |                | Foreign key link to status table            |
+-----------------+--------------+------+-----+---------+----------------+---------------------------------------------+

seasons table
+-------+--------------+------+-----+---------+-------+-----------------------+
| Field | Type         | Null | Key | Default | Extra | Description           |
+-------+--------------+------+-----+---------+-------+-----------------------+
| year  | int(11)      | NO   | PRI | 0       |       | Primary key e.g. 1950 |
| url   | varchar(255) | NO   | UNI |         |       | Season Wikipedia page |
+-------+--------------+------+-----+---------+-------+-----------------------+

status table
+----------+--------------+------+-----+---------+----------------+---------------------------------+
| Field    | Type         | Null | Key | Default | Extra          | Description                     |
+----------+--------------+------+-----+---------+----------------+---------------------------------+
| statusId | int(11)      | NO   | PRI | NULL    | auto_increment | Primary key                     |
| status   | varchar(255) | NO   |     |         |                | Finishing status e.g. "Retired" |
+----------+--------------+------+-----+---------+----------------+---------------------------------+

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
