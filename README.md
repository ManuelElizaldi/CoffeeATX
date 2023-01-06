# CoffeeATX
### Objective:
##### This project's objetive is to use Yelp's API to download coffee shop data in Austin, Texas to then map them based on their review and price in a Tableu dashboard.

### Technologies used:
##### For this project we used the following python packages:
- [Pandas](https://pandas.pydata.org/) To process the data.
- [Requests](https://requests.readthedocs.io/en/latest/) To do the GET requests using Yelp's API.
- [Yelp's API Documentation](https://www.yelp.com/developers) We followed the documentation to develop this project.

### Process:
#### 1) First we accessed the yelp end point -> 'https://api.yelp.com/v3/businesses/{id}', following the documentation's instructions to access only coffeee shops using the corresponding parameters. The file is located in Data/raw_data.csv
#### 2) After extracting the data we used Pandas to do some data wrangling and got the resulting file Data/clean_data.csv
#### 3) From here we used the Latitude and Longitude columns from the data to map them inside our Tableau dashboard which you can accesss here:
- [Dashboard](https://public.tableau.com/app/profile/manuel8857/viz/CoffeShopsAustin/Sheet1)

#### Heres is a sample picture of the Dashboard but I encourage that you go visit the Tableau dashboard!
![Dashboard](/Data/dashboard.png)

### Opportunities for improvement:
#### 1) Each page of data had its own parameters to request the data, to access this I created a variable for each request and then appended all the requests into one dataframe, this could be optimized
