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




My actual data set is composed of 17 rows and 3 columns, meaning that the City of Sydney has a total of 17 different postal codes in its jurisdiction. See below image: <image has been placed on my GitHub document supplied.>


<Source: https://www.cityofsydney.nsw.gov.au/guides/city-at-a-glance>
