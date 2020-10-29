# NPD Activation in Sydney City

## 1. Introduction:

Launching a new product in a competitive marketing requires marketers that are able to be creative and identify the opportunities that will set the brand and new product apart. An Australian Beverages Company is launching a new product - a hypothetical sugar-free spirit that is ready to hit the market. They are targeting younger professionals, that like new trends and will be keen in trying a new drink that will have a confident, fearless, and fun brand. The brand wants to land in the market creating a memorable experience and engage a brand activation agency to support in their launch, and provide the brand with the optimal opportunity to engage with consumers through an experiential marketing activation. 

### 1.1 The Problem: 

A brand agency has been engaged by an alcohol brand to plan an experiential marketing activation in key venues in the City of Sydney. They want to do pop-up bars within these venues to drive customer engagement and brand awareness. The Brand Agency will use data science and FourSquare location to recommend venues to the client. 

### 1.2 Audience / Interest: 

<ul>
<li>Clients: FMCG and Beverages Companies that are looking into doing similar activations.</li>
<li>Businesses: Businesses in diverse industries hospitality, retail that may list their services in FourSquare to show on your searches.</li>
<li>Direct Customer: The customer that will be in the receiving end of the campaign. For a succesful launch you will need to make the right choices of place and drive the engagement.</li>
<li>Local Councils: Wishing to attract similar activations to their councils.</li> 
</ul>

## 2. Data Acquisition

### 2.1 Data Source: 

There is no dataset easily displayed about the City of Sydney Council (as the examples we used on this course), therefore, I am used The City of Sydney Council website to extract the list of suburbs part of the City of Sydney <Source: https://www.cityofsydney.nsw.gov.au/guides/city-at-a-glance>,and the Australian Post website to identifying the postcodes for each suburb. OUr file contains three columns, as follows: 

<ul>
  <li>Postcode: The postcode for each of the suburbs</li> 
  <li>Region: as we are working only with the City of Sydney, there will be only one region in the file. </li> 
  <li>Suburbs: List of suburbs located in the City of Sydney Council.</li> 
</ul>

### 2.2 Data Processing: 

After loading our data set, I have used a few of the components of this course to: 

<ol> 
  <li> Locate duplicated Postal Codes and then append the table to merge this cells into a single row. </li>
  <li> Used the week 2 knowledge to find the Lagitude and Longitude to all of hour suburbs, so we can plot maps. </li>
</ol>

Our database, ready to start a location exploration looks as below: 




