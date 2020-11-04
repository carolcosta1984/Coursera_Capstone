# NPD Alcoholic Beverage: Using FourSquares to indentify venues for an Experiential Marketing Activation in the City of Sydney Area

## 1. Introduction:

Launching a new product requires marketers to be creative and identify opportunities to set the brand and new product apart of the competition. 
In this study we will work with the hypothetical launch of a sugar-free spirit targeting younger professionals, that like new trends and will be keen in trying a new drink that has a confident, fearless, and fun brand to it. The brand wants to launch the product in the market with a memorable experience and engage with their customers through a marketing activation. 

A brand agency has been engaged to identify venues and plan the launch of this new drink. The venues recommended by the marketing company will provide the alcogol company with space to set up pop-up bars and the optimal opportunity to engage with consumers and get the market to try something new, something fun, something fearless! 

### 1.1 The Problem: 

The brand agency has been engaged by the alcohol brand to plan their activation in key venues in the City of Sydney. Their budget will allow to a maximum of 20 pop-up venues and they want in return the venues that will give their New Product the best visibility and return. Their intention is to drive customer engagement and brand awareness, and attract loyal and repeated consumers. 

We will use a data science approach and FourSquare API's to explore the City of Sydney neighbourhoods and identify the top venues in the area to hold the pop-up bars. 

### 1.2 Audience / Interest: 

<ul>
<li>Clients: FMCG / Beverages Companies that are looking into doing similar activations.</li>
<li>Businesses: Businesses in diverse industries including hospitality, retail that may both being a client looking into a similar activation or that will ensure their listing in FourSquare is up-to-date to be contenders on future searches.</li>
<li>Direct Customer: Customer in the receiving end of similar campaigns.</li>
<li>Local Councils: Supporting their local businesses and wishing to attract similar activations to their councils.</li> 
</ul>

## 2. Data Acquisition

### 2.1 Data Source: 

There was no dataset ready for use showing the City of Sydney Council, therefore, we used The City of Sydney Council website to extract the list of suburbs part of the area, and the Australian Post website to identifying the postcodes for each of the suburbs. Our dataframe was them built with three columns: 

<ul>
  <li>Postcode: The postcode for each of the suburbs</li> 
  <li>Region: as we are working only with the City of Sydney, there will be only one region in the file. </li> 
  <li>Suburbs: List of suburbs located in the City of Sydney Council.</li> 
</ul>

Source(s): 
<https://www.cityofsydney.nsw.gov.au/guides/city-at-a-glance>
<https://auspost.com.au/>


### 2.2 Data Processing: 

After loading our data set, we have done some data cleaning and processing: 

<ol> 
  <li> Duplicated Postal Codes: We have identified any suburbs that share the same postal code and applied the groupby function to have unique postal code values. </li>
  <li> Unnamed Column: We have dropped a column that was part of the CSV file, but of no use for this study. </li>
</ol>

The original data set is composed of 17 rows and 3 columns (Including headers). For the purposes of this study, it means we have identified 16 suburbs located within the City of Sydney perimether. Refer to the above image for our initial data set information: 

![](https://github.com/carolcosta1984/Coursera_Capstone/blob/master/Images/Data%20Set.PNG)

### 2.3 Data Processing - Geographical Coordinates:

In order to work with FourSquares I had to find the geographical coordinates (Latitude and Longitude) and ensure that they were added to the dataframe. I have used the <b>pgeocode</b> library.

A new dataframe was created from the pgeocode query containing all geographical information required, then both dataframes have been joining into a new one, that we named <strong>dfgeo</strong>, and a new data cleaning applied to drop any irrelevant columns or duplicated information with the final dataframe as follows: 

![](https://github.com/carolcosta1984/Coursera_Capstone/blob/master/Images/Full%20dfgeo.PNG)

# 3. Methodology: 

After finalizing the data processing and create a data frame, I have used the Foursquare API to find the top venues in the city of Sydney classified as "Nightlife". I have also used K-means clustering to create clusters for the venues with similar characteristics and have plotted maps using both the geopy and and folium libraries to create a maps. 

# 4. Data Analysis: 

# 5. Results: 

# 6. Conclusion: 



