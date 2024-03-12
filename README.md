# liquibase-issue-changeset-with-classpath
Minimally reproducible example of a failed startup if a changeset includes classpath inside the logical file path.

## Steps
1. Execute `mvn liquibase:update`
2. Update the filename in the databasechangelog table to `classpath:test/changelog.xml`#
   1. Note: This is just a workaround for recreating the issue easily
3. Execute `mvn liquibase:update` again
4. Error: `java.nio.file.InvalidPathException: Illegal char <:> at index 9: classpath:changelog.xml`
