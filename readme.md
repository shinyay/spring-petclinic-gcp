# Spring Petclinic for Google Cloud

Spring Petclinig using Cloud SQL on Google Cloud

## Description
### 1. Setup a Cloud SQL (MySQL) instance

Create a new CloudSQL instance

```shell script
$ gcloud sql instances create my-sql
```

Create a database for Pet Clinic
```shell script
$ gcloud sql databases create petclinic --instance my-sql
```

Get the Instance Connection Name of the instance in the format project-id:zone-id:instance-id

```shell script
$ gcloud sql instances describe my-sql |grep connectionName
```

### 2. Add  Cloud SQL Dependency
#### Spring Milestone Repository
```xml
<repository>
  <id>repository.spring.milestone</id>
  <name>Spring Milestones Repository</name>
  <url>http://repo.spring.io/milestone</url>
</repository>
```

#### Spring Cloud GCP Dependency BOM
```xml
<dependencyManagement>
  <dependencies>
    <dependency>
      <groupId>org.springframework.cloud</groupId>
      <artifactId>spring-cloud-gcp-dependencies</artifactId>
      <version>1.0.0.RC1</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>
</dependencyManagement>
```

#### CloudSQL Starter for MySQL
```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-gcp-starter-sql-mysql</artifactId>
</dependency>
```

### 3. MySQL Profile
#### Active profile

Add `spring.profiles.active` in application.properties

```properties
spring.profiles.active=mysql
```

#### application-mysql.properties

```properties
database=mysql
spring.cloud.gcp.sql.database-name=petclinic
spring.cloud.gcp.sql.instance-connection-name=YOUR_CLOUD_SQL_CONNECTION_NAME
spring.datasource.initialization-mode=always
```

### 4. Verify Cloud SQL

```shell script
$ gcloud sql connect my-sql -u root

mysql> use petclinic;
mysql> select * from owners;
```

## Demo

## Features

- feature:1
- feature:2

## Requirement

## Usage

## Installation

## Licence

Released under the [MIT license](https://gist.githubusercontent.com/shinyay/56e54ee4c0e22db8211e05e70a63247e/raw/34c6fdd50d54aa8e23560c296424aeb61599aa71/LICENSE)

## Author

[shinyay](https://github.com/shinyay)
