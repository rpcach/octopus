
<!-- README.md is generated from README.Rmd. Please edit that file -->

# octopus <img src="images/octopus_logo_2.png" align="right" height="138"/>

<!-- badges: start -->

[![R-CMD-check](https://github.com/MCodrescu/octopus/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/MCodrescu/octopus/actions/workflows/R-CMD-check.yaml)
[![CRAN
status](https://www.r-pkg.org/badges/version/octopus)](https://CRAN.R-project.org/package=octopus)

<!-- badges: end -->
<!-- change -->

The *octopus* package is a database management tool built entirely in R.
You can preview tables, upload files, send queries, and more.

All database credentials are handled by the R user. Simply pass a
supported database connection object created with `DBI::dbConnect()` to
the function `octopus::view_database()` and *octopus* will start a shiny
application allowing you to interact with the database.

*Try it out here!
[shinyapps.io](https://zszxyy-marcus-codrescu.shinyapps.io/octopusconceptapp/)*

![octopus Interface](images/octopusMainPage3.png)

## Supported Databases

The *octopus* package currently supports the following databases:

- Postgres

- MySQL

- SQLite

- DuckDB

- Snowflake

- Vertica DB

## Installation

Install the stable version from CRAN.

``` r
install.packages("octopus")
```

Install the development version from github.

``` r
devtools::install_github("MCodrescu/octopus")
```

## Example

Here is an example of connecting to a database and running the main
function of octopus.

``` r
# Create a Database Connection
drv <- duckdb::duckdb()
con <- DBI::dbConnect(drv)

# Write some data
DBI::dbWriteTable(con, "mtcars", mtcars)

# View the Database
octopus::view_database(con)
```
