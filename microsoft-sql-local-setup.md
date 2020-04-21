# Microsoft SQL Server local setup


## Installation.

#### For Windows:

There are 2 ways to run MSSQL on Windows:

-   Download and Install Developer edition from here: [https://www.microsoft.com/en-us/sql-server/sql-server-downloads](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
    
-   Run MSSQL in Docker. Image description is here: [https://hub.docker.com/_/microsoft-mssql-server](https://hub.docker.com/_/microsoft-mssql-server)
    

#### For MacOS:

Run MSSQL in Docker. Image description is here: [https://hub.docker.com/_/microsoft-mssql-server](https://hub.docker.com/_/microsoft-mssql-server)

#### For Linux:

Run MSSQL in Docker. Image description is here: [https://hub.docker.com/_/microsoft-mssql-server](https://hub.docker.com/_/microsoft-mssql-server)

## Configuration.
You need to connect to Microsoft SQL Server and create a database for the OpenMAVN project. It is possible to use a single database for all services because each service uses its own database schema. Each service creates (and keeps up-to-date) a set of tables that are required for this concrete service.   

In order to create the database you can use command line tools or GUI like [Microsoft SQL Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15) (Windows only), [Azure Data Studio](https://docs.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver15) (Cross platform), [DBeaver](https://dbeaver.io/download/) (Cross platform) or any other you like. It is enough to create an empty database.   

Then you can build a [connection string](https://www.connectionstrings.com/sql-server/) and put it into the service setting file.
