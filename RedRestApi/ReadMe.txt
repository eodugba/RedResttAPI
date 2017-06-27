Purpose:  This is a springboot application was created to demonstrate the use of REST API webservices on a webpage.
          Application displays cities a user has visited on a google map using provided logitude and latitude.
           

Technology:  Java 1.8, Angular 1, Javascript, SpringBoot, Postgres, H2 database,hibernate

Database:  Currently using built in H2 database but was initially built using postgres
           application tables:  City - All cities visited by all users with the longitude and latitude cordinates.
                                       columns: city_id, date_added, date_time_added, lastupdated,latitude,longitude,city_name,state_id, status;
                                       primary key : city_id,state_id
                                       foreign keys:  state_id  (state table)
                                State - All states in the US.
                                        columns: state_id,abbreviation,date_added,date_time_added,lastupdated,state_name;
                                        primary key: state_id,state_name
                                UserData - All User information    
                                           columns: user_id,date_added,date_time_added,first_name_last_name,lastupdated;
                                           primary_key: user_id
                                UserLogin - All user login information
                                            columns:  user_id,password,user_name
                                            primary key: user_name
                                            foreign key: userid (userdata table)
                                visits - All cities visited by user
                                         columns: visit_id,city_id,date_time_added,date_visited,lastupdated,state_id,user_id 
                                         primary key: visit_id
                                         foreign key:  city_id (city table),state_id (state_table), user_id (userdata table);
      
Functionality:  1.  Stand up rest services for all tables within the database.
                    a. Ability to retrieve data for all contents
                    b. Ability to retrieve data for a given primary key
                    c. Ability to modify table data via rest calls.
                    d. Ability to add/delete data via rest calls.
                2.  Create WEBPAGE to display rest call results.
                    a.  Created a page to log a user into the application
                    b.  Displayed a user visit on a map
                    c.  Provided additional detail about visit in a table format
Things to do or Consider:
	1.  The security needs to be better.  Use Spring Security Token based Authentication
	2.  Enhanced WebPage to allow clicking of a location to update a user's city visited data via the REST POST service provided.
	3.  Prevent and remove duplicate visits from being inserted in the visit table
	4.  Share visits and/or compare with other users
	5.	Create alerts to notify users when a friend is close by.
	
	
Build:
     execute mvn clean install package 

Execute
  java -jar target RedRestApi-0.0.1-SNAPSHOT.ja

                    
                    

