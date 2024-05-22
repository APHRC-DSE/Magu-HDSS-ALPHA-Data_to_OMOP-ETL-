#install.packages("remotes")
````R
remotes::install_github("OHDSI/Achilles")
library(remotes)
````
#set JDBC drivers
````R
Sys.setenv("DATABASECONNECTOR_JAR_FOLDER" = "c:/temp/jdbcDrivers")
````

#create connection
````R
connectiondetails <- DatabaseConnector::createConnectionDetails(
  dbms = "postgresql",
  server = "localhost/alpha",
  user = "postgres",
  password = "aphrc",
  port = 5432,
  pathToDriver = "c:/temp/jdbcDrivers"
)
````
#set output folder 
````R
outputFolder <- "output"
````

#run achilles
````R
Achilles::achilles(connectionDetails = connectiondetails,
                   cdmDatabaseSchema = "public",
                   resultsDatabaseSchema = "achillesresults",  #no capital letters- brings issues with postgres
                   sourceName = "cdm",
                   createTable = TRUE,
                   smallCellCount = 5,
                   cdmVersion = 5.4,
                   numThreads = 1,
                   outputFolder = outputFolder)
````



                       
