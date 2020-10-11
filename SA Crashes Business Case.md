# Report: Predicting the Severity of Crashes in South Australia  

### Discussing possibilities to reduce accidents numbers and better allocate traffic control resources


#### 1. Introduction 

##### 1.1 Background

According to the WHO (World Health Organization), approximately 1.35 million people die each year victim of road accidents, with another 20+ million people suffering some kind of non-fatal injury from traffic crashes. Road traffic injuries are also the leading cause of death for children and young adults aged 5-29 years old, making it a problem to governments all over the world. Road traffic injuries can cause considerable economic losses to families and individuals and cost to most countries around 3% of their gross domestic product. 

During 2019, from January to December, South Australia has seen 12,964 accidents with 114 fatalities and 6031 casualities, and both crashes and injuries can be prevented using data to predict the variables that influence on accidents. The allocation of resources such as traffic controllers and police, improvenents in the transport and roads planning, increase in public awareness, and identification of risk factors are all factors that can contribute to a reduction on number of accidents, consequently creating a more secure environment and saving lives.

##### 1.2 Problem

Through this study we want to identify the most relevant variables contributing to road crashes in South Australia (SA), and using the finds from this variable pose suggestions on the type of initiatives that can be applied to reduce accidents and move towards more secure roads. 

##### 1.3 Audience / Interest: 

The Government of South Australia and Australian Government - A proposed model to predict when and where accidents are more likely to happen will support the govenment on deciding how to allocate resources and reduce the burden on the economy caused by traffic crashes.



#### 2. Data Acquisition and Cleaning

##### 2.1 Data Source

The data set has been acquired from an open source and is available from the Government of South Australiaa through the website of the Department of Infrastructure and Transport. Source: https://www.dpti.sa.gov.au/

##### 2.2 About the Data Set

The data set include information on crashes that happened in South Australia during 2019 and include details on type of crash, number or units involved on the accident, if the person causing or involved in the accident was under influencing, day of the week, time, type of road, weather conditions, speed limit on the area, traffic control conditions and severity of the crashes, and information on severity of causualities.

The data set before claening has 12965 rowss and 33 columns, including headers. More invormation on the data and a description of all fields included below: 


<table>
  <tr>
  <th left-align> Column Name </th> 
  <th left-align> Info about data</th>
  <th left-align> Number of Data Entries</th>
  </tr>
  <tr>
    <td> REPORT_ID</td>
    <td> Unique number assigned to records to separate individual crashes </td>
    <td> 12964 </td>
  </tr>
  <tr>
    <td>Stats Area</td>
    <td>A code defining whether the road crash occurred within City, Metro or Country Area</td>
    <td> 12964 </td>
  </tr>
  <tr>
    <td> Suburb </td>
    <td> The Suburb that the crash occurred in</td>
    <td>12964 </td>
  </tr>
  <tr>
    <td> Postcode </td>
    <td> The Postcode that the crash occurred in </td>
    <td> 12964 </td>
  </tr>
  <tr>
    <td> LGA Name </td>
    <td> The Local Government Area that the crash occurred in</td>
    <td> 12857 </td>
  </tr>
  <tr>
    <td> Total Units </td>
    <td> The total number of units involved in a road crash</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Total Cas </td>
    <td> Stands for Total Casualities. Total number of casualties (fatalities and treated injuries) as a result of a road crash</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Total Fats </td>
    <td> Stands for Total Fatalities. Total number of fatalities as a result of a road crash</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Total SI </td>
    <td> Stands for Total Serious Injuries. Total number of people admitted to hospital with overnight stay as a result of a road crash</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Total MI </td>
    <td> Stands for Total Minor Injuries. Total number of people treated by private doctor or treated at hospital but not admitted</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Year </td>
    <td> Year of the crash</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Month </td>
    <td> Month in which the accident took place</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Day </td>
    <td> The day of the week the crash occurred </td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Time </td>
    <td> The reported time of the crash </td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Area Speed </td>
    <td> The speed limit at the time and location of the crash </td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Position Type </td>
    <td> Identifying if a crash location was at an intersection or midblock </td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Horizontal Align </td>
    <td> Defines the horizontal alignment of the road at the sight of the crash </td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Vertical Align </td>
    <td> Defines the vertical alignment of the road at the sight of the crash </td>
    <td> 12964 </td>
  </tr>
 <tr>
    <td> Other Feat </td>
    <td> Defines other relevant features of the crash site locations </td>
    <td> 12964 </td>
  </tr>
 <tr>
    <td> Road Surface </td>
    <td> Defines the road surface type at the crash location</td>
    <td> 12964 </td>
  </tr>
 <tr>
    <td> Moisture Cond </td>
    <td> Defines the pavement surface moisture condition at the crash location</td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> Weather Cond </td>
    <td> Defines the weather condition at the time and location of the crash </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> DayNight </td>
    <td> The lighting condition at the time and location of the crash </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> Crash Type </td>
    <td> Defines the road crash type </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> Unit Resp </td>
    <td> The number of the unit determined to be responsible for the road crash </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> Entity Code </td>
    <td> A code defining the entity deemed to be responsible for the road crash</td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> CSEF Severity </td>
    <td>Defines the road crash severity (classified by the highest injury severity sustained in the crash). Decoded values:“3: SI” = Serious Injury, “2: MI” = Minor Injury, “1: PDO”= Property Damage Only </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> Traffic Ctrls </td>
    <td> Defines the traffic control at the time and location of the road crash </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> DUI Involved </td>
    <td> Involved if at least one controller in the crash recorded an illegal Blood Alcohol Concentration level</td>
    <td> 349 </td>
  </tr>  
<tr>
<tr>  
    <td> Drugs Involved </td>
    <td> Involved if at least one controller in the crash tested positive for a prescribed drug (THC (cannabis), methylamphetamine (speed, ice or crystal meth) or MDMA (ecstasy))</td>
    <td> 314 </td>
  </tr>  
<tr> 
    <td> ACCLOC_X  </td>
    <td> The Y coordinate of the crash when located</td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> ACCLOC_Y</td>
    <td> The Y coordinate of the crash when located</td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> UNIQUE_LOC  </td>
    <td> A concatenation of the X and Y coordinates for the purpose of grouping crashes</td>
    <td> 12964 </td>
  </tr>  
</table>


##### 2.3 Data Cleaning:

For the purpose of this report we have dropped the following columns on the data set: REPORT_ID, Postcode, LGA Name, Year, Horizontal Align, Vertical Align, Other Feat, Crash Type, Unit Resp, Entity Code, CSEF Severity, ACCLOC_X, ACCLOC_Y, UNIQUE_LOC. We have also 

Both, DUI Ivolved and Drugs Involved columns will also be combined into a new column that will be named as 'Under Influence' and will be used to find the relationship between the use of substances and traffic crashes as well as its severity. 


#### 3. Exploratory Data Analysis: 


<ol>
  <li>What are the most relevant elements that contribute to road accidents?</li>
  <li>Would the time of the day or day of the week influence when an accident happen?</li>
  <li>What about the road conditions? The fact of a road being sealed or unsealed influence in accidents severity?</li>
<li>Does rain impact on number of accidents?</li>
<li>In case of accidents involving abuse of substances such as alcohol or drugs - what is the impact on the severity of a crash?</li>
<li>Are there areas that require more attention do to higher concentration of accidents in the region? If so, what are the conditions in which accidents happen and what can we do to improve. ie. Reduce Speed Limit.</li>
<li>Based on day of the week and location, how can we better allocate resources such as traffic controllers and police to a region to reduce risks of accident?</li>
</ol>

