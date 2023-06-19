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
    - `headers = {"Authorization": f"Bearer {api_key}"}`
5) Once you have set up the necessary components, you can utilize the requests library to access the URL: `https://api.yelp.com/v3/businesses/search` like so:
    - `r = requests.get(url = url, params = parameters, headers = headers)`
6) If your request is successful, you will receive a JSON response containing businesses that match the parameters you have set up. This JSON can be parsed into a dataframe and saved as the basis for our Tableau dashboard.

# Dashboard 
This is the dashboard I have created to visualize and map all the coffee shops. Feel free to explore the data!
   -[Dashboard](https://public.tableau.com/app/profile/manuel8857/viz/CoffeShopsAustin/Sheet1)

## Analysis:
- Each circle represents a coffee shop, and the size of the circle corresponds to the number of reviews it has. This can serve as an indicator of the coffee shop's popularity.

- The color of the circle represents the price range, ranging from yellow to red. Yellow indicates a more affordable coffee shop, orange indicates a medium price range, and red indicates the most expensive. It's important to note that these price range categories were determined by Yelp (cheap $, medium $$, expensive $$$). The classification is based on the overall goods sold in the coffee shop, not just the coffee beverages.

![Dashboard](/Data/dashboard.png)

# Areas of improvement:
- Each page of data had its own set of parameters for requesting the data. To access this information, I created a variable for each request and then merged all the requests into a single dataframe. However, there is room for optimization in this process.
