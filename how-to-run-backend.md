# How to run backend

### Step 1. Identify project dependencies.

Each .NET Core project should contain the file “settings.yaml” which is a setting template. Based on this file you can understand what external dependencies the current project has. First yaml node indicates the current project and it’s internal dependencies like database, cache or queue broker. Other nodes that usually contain “ServiceUrl”, “ServiceClient” are pointing to other services.

### Step 2. Satisfy project dependencies.

Each .NET Core project should contain file “settings.json” which is a configuration file based on the “settings.yaml” template. You should modify this file locally (do not forget to add this file to .gitignore) and pass all setting values it requires which can be:

-   Microsoft SQL Server connection string. [Set up instruction](https://github.com/OpenMAVN/Welcome/blob/master/microsoft-sql-local-setup.md)
   
-   Redis connection string. [Set up instruction](https://github.com/OpenMAVN/Welcome/blob/master/redis-local-setup.md)
   
-   RabbitMQ connection string. [Set up instruction](https://github.com/OpenMAVN/Welcome/blob/master/rabbitmq-local-setup.md)

-   AzureStorage connection string. [Set up instruction](https://github.com/OpenMAVN/Welcome/blob/master/azure-storage-local-setup.md)
    
-   Dependent service URL. [Set up instruction](https://github.com/OpenMAVN/Welcome/blob/master/dependent-service-configuration.md)
    

### Step 3. Run the project.

Now when project settings are configured we are ready to run the project. In order for the project to run with local “settings.json” you need to point the project to this file using an environment variable called “SettingsUrl”.

Some projects require an additional environment variable called “ENV_INFO” which should contain any identification of you. This value is used when you are connecting to a development kubernetes cluster using VPN.

### Step 4. Interact with a running project.

Each .NET Core project is HTTP API service. So it does not have a personal GUI to interact with. But you should be able to send requests to it and get responses using Swagger UI (general information about [Swagger UI](https://swagger.io/tools/swagger-ui/) which is hosted on [http|https]://[yourhost]:[port]/swagger/ui.