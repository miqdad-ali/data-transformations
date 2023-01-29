# Data Transformation Project

This project is a starting point for automating the process of transforming data from any raw source to a Postgres database, using Airbyte and dbt. With this setup, you can easily replicate data from various sources to a destination of your choice, and perform data transformations on the replicated data.
More on Airbyte: [Airbyte documentation](https://www.airbyte.io/docs/)
More on dbt: [DBT documentation](https://docs.getdbt.com/)

## Prerequisites
1. Docker
2. dbt postgres adapter: pip install dbt-postgres

## Getting Started
1. Clone this repository to your local machine: git clone https://github.com/miqdad-ali/data-transformation.git
2. Navigate data-transformation
3. Edit the `.env` file in the root of the repository and set the environment variables for your use case. Check the examples:
    - Connection details for "raw" postgres container:
        - POSTGRES_RAW_USER=myuser
        - POSTGRES_RAW_PASSWORD=mypassword
        - POSTGRES_RAW_DB=rawdata
        - POSTGRES_RAW_PORT=5432
    - Connection details for "clean" postgres container:
        - POSTGRES_CLEAN_USER=myuser
        - POSTGRES_CLEAN_PASSWORD=mypassword
        - POSTGRES_CLEAN_DB=cleandata
        - POSTGRES_CLEAN_PORT=5433
    - Airbyte configuration:
        - AIRBYTE_HOST_PORT=8000
       
4. Build and start the containers using `docker-compose`: docker-compose up --build
5. Once the containers are up and running, you can access the Postgres databases via the host `localhost` and the configured ports in the `docker-compose.yml` file.


## Note
- This is just an example of how you might set up the project, and it may not be an exact representation of the environment variables and configurations that you need for your specific use case.
- The environment in this example will run two postgres containers one for the raw data and another for the transformed data, but this is flexible and you can use any number of containers you want.
- Make sure to also update the docker-compose file with the right configurations and ports.


