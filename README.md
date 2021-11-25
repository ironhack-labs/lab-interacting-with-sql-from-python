![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Interacting with SQL from Python

In this lab, you will be using the [Sakila](https://dev.mysql.com/doc/sakila/en/) database of movie rentals. You have been using this database for a couple of labs already, but if you need to get the data again, refer to the official [installation link](https://dev.mysql.com/doc/sakila/en/sakila-installation.html).

The database is structured as follows:

<br>

![DB schema](https://education-team-2020.s3-eu-west-1.amazonaws.com/data-analytics/database-sakila-schema.png)

<br>

### Instructions

In this lab, we will find the customers who were active in consecutive months of May and June. Follow the steps to complete the analysis.

1. Create a connection between Python and the Sakila database.
2. Create Python function named `rentals_may` to connect to the Sakila database and return dataframe storing the data from `rental` table with information for May 2005.
3. Create Python function named `rentals_june` to connect to the Sakila database and return dataframe storing the data from `rental` table with information for June 2005.
4. Create a Python function to get the number of rentals for each customer in May given the dataframe provided by the function `rentals_may`.
Hint: Consider making use of pandas [groupby()](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html) and pandas [`agg()`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.agg.html?highlight=agg#pandas.DataFrame.agg)
5. Create a Python function to get the number of rentals for each customer in June given the dataframe provided by the function `rentals_june`.
6. Write a Python function named `check_rentals` that given: 
  - a dataframe with the number of rentals in May by each `customer_id` 
  - a dataframe with the number of rentals in June by each `customer_id` 
    return a new dataframe with the following columns:
    - `customer_id` 
    - `Rentals_May`
    - `Rental_June`
    - The difference between the previous columns

  **Hint**: For this part, you can create a join between the two dataframes created before, using the merge function available for pandas dataframes. Here is a link to the documentation for the [merge function](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html).

7. Create a Python function that given the dataframe returned by the previous function, returns another dataframe with the `customer_id` of customers who rented movies in may but didn't rent any movie in June.