# Cyclistic-bike-share-analysis-case-stud

SELECT 
	COUNT (DISTINCT ride_id)
FROM 'Cyclistic_bike.Cyclistic_data2`

#check for null row 
SELECT COUNT (*) 
FROM `Cyclistic_bike.Cyclistic_data2` 
WHERE START_STATION_ID IS NULL OR START_STATION_NAME IS NULL;

DELETE start_station_name
FROM `Cyclistic_bike.Cyclistic_data2`

#Inspect the member_casual column
SELECT
  DISTINCT member_casual
FROM
  `Cyclistic_bike.Cyclistic_data2`;

	# Inspect the length column 
	SELECT
  MIN(ride_length) AS min_length,
  MAX(ride_length) AS max_length
FROM
 `Cyclistic_bike.Cyclistic_Copy`;

# Check to see if the start_station_name column contains null values using this query
SELECT
  *
FROM
 `Cyclistic_bike.Cyclistic_Copy`

WHERE 

 start_station_name IS NULL;

 # Identify potential errors
 SELECT
  DISTINCT member_casual
FROM
  `Cyclistic_bike.Cyclistic_Copy`;

	DELETE from member_casual
	where member_casual is null;

	# use MIN and MAX to check if that’s correct
SELECT
  MIN(ride_length) AS min_ride_length,
  MAX(ride_length) AS max_ride_length
FROM
`Cyclistic_bike.Cyclistic_Copy`;

# Count how many rows you would be deleting

SELECT

   COUNT(*) AS num_of_rows_to_delete

FROM

   `Cyclistic_bike.Cyclistic_Copy`

WHERE

   start_station_name = NULL;

#delete that row using this query:  

DELETE start_station_name

WHERE start_station_name is NULL;

#Check the ride_length column for inconsistencies by running a query with a SELECT DISTINCT statement: 

 SELECT
  DISTINCT ride_length
	FROM `Cyclistic_bike.Cyclistic_Copy`;

# Use a LENGTH statement to determine the length of how long each of these string variables: 

SELECT
  DISTINCT ride_length,
  LENGTH(ride_length) AS string_length
FROM
  `Cyclistic_bike.Cyclistic_Copy`;

#use the TRIM function to remove all extra spaces in the drive_wheels column 

UPDATE

  `Cyclistic_bike.Cyclistic_Copy`

SET

  ride_length = TRIM(ride_length)

WHERE TRUE;

#DROP columns in table `Cyclistic_bike.Cyclistic_Copy`.

ALTER TABLE `Cyclistic_bike.Cyclistic_Copy`
DROP COLUMN start_station_name;

ALTER TABLE `Cyclistic_bike.Cyclistic_data2`
DROP COLUMN start_station_id

ALTER TABLE `Cyclistic_bike.Cyclistic_data2`
DROP COLUMN end_station_name

ALTER TABLE `Cyclistic_bike.Cyclistic_data2`
DROP COLUMN end_station_id

#To ADD one column day_of_week 
ALTER TABLE `Cyclistic_bike.Cyclistic_data2` ADD (day_of_week(20));

# MODIFY column week_of_day in table `Cyclistic_bike.Cyclistic_data2`

ALTER TABLE `Cyclistic_bike.Cyclistic_data2` MODIFY week_of_day varchar(20);
