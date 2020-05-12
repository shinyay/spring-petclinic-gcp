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
