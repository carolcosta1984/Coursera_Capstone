# NPD Activation in the City of Sydney Area

## 1. Introduction:

Launching a new product in a competitive market requires marketers to think creative, identifying opportunities that will drive brand engagement and new product knowledge and as a result set the product apart of its competition. 

In this project we have a ficticious beverage company that wants to launch their new sugar-free spirit, with a brand that is confident, fearless and fun with a memorable experience. The product is ready to hit the market, and they are targeting an audience formed by younger professionals, looking for an alternative/better for you alcohol drink, and that are keen in trying new and trendy things.

The company has engaged a brand agency to suggest and negotiate on their behalf space on key venues in the City of Sydney Area for the set up of "Summer Pop-Up Bars". The engaged agency will use one of it's data scientists and his/her knowledge of Foursquare, a location based application, to recommend venues to the client, through the exploration of the area where the activation will happen. 

### 1.1 Audiences: 

This type of solution would appeal to a range of companies in a similar situation and is one of the many uses for the Foursquare application, including: 

<ul>
<li> FMCG Companies looking for similar services / activations.</li>
<li> Businesses in industires such as hospitality, retail, events that may use a similar code to explore alternatives in an area.</li>
<li> Consummers that will be the receives of a campaign.</li>
<li> Local government / councils wishing to attract similar activations to their areas.</li>
</ul>

## 2. Data: 

I used the City of Sydney Council website to extract the list of suburbs part of the area and the Australian Post website to identifying the postcodes for each suburb and put together a CSV file with three different columns: 

<ul>
<li> Postcode: The postcode for each of Suburb.</li>
<li> Region: As we are exclusive working with the City of Sydney for this project, it will be the only region in the file. </li>
<li> Suburbs: List of suburbs located in the City of Sydney Council area.</li>
</ul>


### Data Processing:

After loading the data set, I have processed and cleaned the databases to get a dataframe that was adequate to work with geographical data. Some observations below: 

<ul> 
  <li> The initial CSV file when loaded to Jupyter notebooks have an unnamed column. The first thing done in the data cleaning was to apply the <b> .drop</b> function to remove the column.</li>
  <li> I have them used the <b>value_counts</b> function on the postcodes to identify any suburbs thatwere located on a similar postcode and combined them into a single line using a <b>groupby</b>. </li>
</ul>

The initial data cleanse, resulted on the dataframe below: 

![](https://github.com/carolcosta1984/Coursera_Capstone/blob/master/Images/Data%20Set.PNG)

The data set is composed of 17 rows and 3 columns including headers. This means that the City of Sydney has a total of 16 different postal codes in its jurisdiction.

### Data Sources: 
<ul>
  <li><b>City of Sydney:</b> https://www.cityofsydney.nsw.gov.au/guides/city-at-a-glance</li>
  <li><b>Australian Post:</b> https://auspost.com.au/</li>
 </ul>
 
 ## 3. Methodology:
 
In order to identifying venues to make recommendations to our client, I used the location data technology that enables you to work with geographical data - Foursquare, and for the puporse of this study it was the solely method used, allowing us to identifying venues and plot maps with "all locations" and a "limited number of locations". 

## 4. Results: 

With our original dataframe built, the next step of our data was to find out the latitude and longitude for all of our neighborhoods. I have used the query system <b>geocode</b> and saved the results in a separate dataframe, that once finalized I applied the <b>pd.concat</b> function to join with our original dataframe. The result after the dataframes were combined, any relevant columns were dropped or renamed, was the dataset below: 

![](https://github.com/carolcosta1984/Coursera_Capstone/blob/master/Images/Full%20dfgeo.PNG)

With my dataset updated with the geographic coordinates and all required libraries installed, I started by finding the City of Sydney coordinates and creating a map with the Suburbs in our dataframe plotted to it, so we could ensure that all our data was correct. The initial map looked as the below: 

![](https://github.com/carolcosta1984/Coursera_Capstone/blob/master/Images/City%20of%20Sydney%20with%20postcodes%20plotted.PNG)

As in this project, we were looking in identifying venues that would allow alcoholic drinks to be served, I have done some research on how I could best use the Foursquare application to narrow down my search only to venues that would be able to feature our pop-up bars. 

In my Foursquare link, I have applied the <b>explore</b> option to return the list of recommended venues within the City of Sydney Area, and have also applied the following parameters to narrow down my search:

<ul> 
  <li> Latitude/Longitude: <b>ll</b> - ensuring that the link would return venues for the area we were looking for.</li>
  <li> Radius: <b>radius </b> - distance to look within metres.</li> 
  <li> Section: <b>section</b> - Foursquare allows you to chose a section in order to limit your results to venues of a specific category. You can choose from food, drinks, coffee, shops, arts, outdoors, sights, trending, nextVenues (venues frequently visited after a given venue), or topPicks (a mix of recommendations generated without a query from the user). I have used the topPicks in our project. </li> 
  <li>Category ID: <b>categoryId</b> - In order to help narrow down the search, you can also limit the category you wish to search. In this project we have used the specific ID for "Nightlife Spots".</li>
  <li> Query: <b>query</b> 	Allows you to add a term to be searched against a venue's tips, category, etc. The query parameter has no effect when a section is specified.</li>
  <li> Time: <b>time</b> Foursquare basically operates on your local time, so as I wanted to identifying nightlife spots, my results were not accurate in the beginning. The solution I figured was to set up on my search link the time as a parameter. When you set the time parameter to "any", Foursquare will retrieve results for any time of day, instead of only your current time.</li>
  <li> Day: <b>day</b> - Similar to the time parameter, I set the day to "any" allowing be to observe not only venues that were open on the day of the week I was doing my consultation. </li>
  </ul> 
  
  
sortByPopularity = 1
