### Using liquibase

#### Added the following plugin:
id 'org.liquibase.gradle' version '2.2.0'

#### Added the following dependencies:
liquibaseRuntime 'info.picocli:picocli:4.6.1'
liquibaseRuntime 'org.liquibase:liquibase-core'
liquibaseRuntime 'org.postgresql:postgresql'

* `./gradlew generateChangelog`

### Dump the data into a file
`kubectl exec -it postgres-0 -- /bin/bash`

Make a dump of the DB
`pg_dump -U admin -d postgresdb  --data-only --column-inserts > data.sql`
`pg_dump -U admin -d postgresdb  --data-only -t tutorial -t article -t comment --column-inserts > data.sql`

#### Copy the file from k8s to your local machine
* `kubectl cp postgres-0:/data.sql ./data.sql`

### To view tables
`psql --username=admin postgresdb`


`./gradlew clean build`
`./gradlew bootBuildImage --imageName moldovean/greetings-liquibase`
`docker push moldovean/greetings-liquibase`

### TODO
Get the data inside the postgres pod
* kubectl exec -i postgres-pod -n my-namespace -- psql -U postgres -d my_database < data.sql

