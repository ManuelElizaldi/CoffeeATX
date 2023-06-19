# Project Description
I initially developed this project when I relocated to the wonderful city of Austin, Texas. Being a coffee enthusiast, I was aware that there were numerous adventures awaiting me, thanks to the passionate community that surrounds this delightful caffeinated beverage. However, since I didn't know anyone who could assist me in navigating the extensive selection of coffee shops this city offers, I decided to create a personal tool to guide me through this exciting experience.

# Objective
The objective of this project is to utilize Yelp's API to acquire coffee shop data in Austin, Texas, and its surrounding areas. The collected data will then be mapped on a Tableau dashboard, taking into account reviews and pricing information as the mapping criteria.

# Technologies Used 
## Programming Language
- Python 3.8.5
## Dashboard
- Tableau
## Packages
- Pandas 1.1.3
- numpy 1.22.4
- Requests 2.28.2
## Relevant Documentation
- [Yelp's API Documentation](https://www.yelp.com/developers).

# Project Set up
1) Sign up for a Yelp developer account [here](https://www.yelp.com/developers) and create an app on this [page](https://www.yelp.com/developers/v3/manage_app).
2) After filling out the forms, you will receive your API key and Client ID. Remember to save them for later use.
3) Depending on your requirements, configure your parameters as follows:
    - `{'term':'coffee shop','limit':50,'offset':10,'radius':40000,'location':'Austin'}`
4) For the request, set your headers like so:
    - `headers = {'Authorization':'bearer %s' % api_key}` 

1) First we accessed the yelp end point -> 'https://api.yelp.com/v3/businesses/{id}', following the documentation's instructions to access only coffeee shops using the corresponding parameters. The file is located in Data/raw_data.csv
2) After extracting the data we used Pandas to do some data wrangling and got the resulting file Data/clean_data.csv
3) From here we used the Latitude and Longitude columns from the data to map them inside our Tableau dashboard which you can accesss here:
- [Dashboard](https://public.tableau.com/app/profile/manuel8857/viz/CoffeShopsAustin/Sheet1)

# Dashboard 
Heres is a sample picture of the Dashboard but I encourage that you go visit the Tableau dashboard!
## How to read this dashboard:
#### - Each circle is a coffee shop, the bigger the circle, the more reviews it has, this could indicate the popularity of the coffee shop. 
#### - The color of the circle indicates the price range, going from yellow to red. Yellow indicates a cheaper coffee shop, orange indicates a medium price range and red indicates the most expensive. Note: the price range bins where determined by Yelp (cheap $, medium $$, expensive $$$) and their classification  is established by the overall goods sold in the coffee shop and not just the coffee beverages. 
![Dashboard](/Data/dashboard.png)

### Opportunities for improvement:
#### 1) Each page of data had its own parameters to request the data, to access this I created a variable for each request and then appended all the requests into one dataframe, this could be optimized
