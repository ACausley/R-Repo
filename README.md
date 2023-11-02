# R-Repo

## use to connect R studio to UDAL

install.packages("rstudioapi")
library(DBI)
server <- "udalsyndataprod.sql.azuresynapse.net"
database = "UDAL_Warehouse"
con <- DBI::dbConnect(odbc::odbc(),
                      UID = rstudioapi::askForPassword("aaron.causley@udal.nhs.uk"),
                      Driver="ODBC Driver 17 for SQL Server",
                      Server = server, Database = database,
                      Authentication = "ActiveDirectoryInteractive") 
