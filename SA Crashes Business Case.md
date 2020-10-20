# Report: Predicting the Severity of Crashes in South Australia  

## Discussions on how to reduce accidents numbers and better allocate traffic control resources


### 1. Introduction 

#### 1.1 Background

According to the WHO (World Health Organization), approximately 1.35 million people die each year victim of road accidents, with another 20+ million people suffering some kind of non-fatal injury from traffic crashes. Road traffic injuries are also the leading cause of death for children and young adults aged 5-29 years old, making it a problem to governments all over the world. Road traffic injuries can cause considerable economic losses to families and individuals and cost to most countries around 3% of their gross domestic product. 

During 2019, from January to December, South Australia has seen 12,964 accidents with 114 fatalities and 6031 casualities, and both crashes and injuries can be prevented using data to predict the variables that influence on accidents. The allocation of resources such as traffic controllers and police, improvenents in the transport and roads planning, increase in public awareness, and identification of risk factors are all factors that can contribute to a reduction on number of accidents, consequently creating a more secure environment and saving lives.

#### 1.2 Problem

Through this study we want to identify the most relevant variables contributing to road crashes in South Australia (SA), and using the finds from this variable pose suggestions on the type of initiatives that can be applied to reduce accidents and move towards more secure roads. 

#### 1.3 Audience / Interest: 

The Government of South Australia and Australian Government - A proposed model to predict when and where accidents are more likely to happen will support the govenment on deciding how to allocate resources and reduce the burden on the economy caused by traffic crashes.



### 2. Data Acquisition and Cleaning

#### 2.1 Data Source

The data set has been acquired from an open source and is available from the Government of South Australiaa through the website of the Department of Infrastructure and Transport. Source: https://www.dpti.sa.gov.au/

#### 2.2 About the Data Set

The data set include information on crashes that happened in South Australia during 2019 and include details on type of crash, number or units involved on the accident, if the person causing or involved in the accident was under influencing, day of the week, time, type of road, weather conditions, speed limit on the area, traffic control conditions and severity of the crashes, and information on severity of causualities.

The data set before cleaning has 12965 rows and 33 columns, including headers. More invormation on the data and a description of all fields included below: 


<table>
  <tr>
  <th left-align> Column Name </th> 
  <th left-align> Info about data</th>
    </tr>
  <tr>
    <td> REPORT_ID</td>
    <td> Unique number assigned to records to separate individual crashes </td>
    </tr>
  <tr>
    <td>Stats Area</td>
    <td>A code defining whether the road crash occurred within City, Metro or Country Area</td>
   </tr>
  <tr>
    <td> Suburb </td>
    <td> The Suburb that the crash occurred in</td>
  </tr>
  <tr>
    <td> Postcode </td>
    <td> The Postcode that the crash occurred in </td>
  </tr>
  <tr>
    <td> LGA Name </td>
    <td> The Local Government Area that the crash occurred in</td>
  </tr>
  <tr>
    <td> Total Units </td>
    <td> The total number of units involved in a road crash</td>
  </tr>
<tr>
    <td> Total Cas </td>
    <td> Stands for Total Casualities. Total number of casualties (fatalities and treated injuries) as a result of a road crash</td>
  </tr>
<tr>
    <td> Total Fats </td>
    <td> Stands for Total Fatalities. Total number of fatalities as a result of a road crash</td>
  </tr>
<tr>
    <td> Total SI </td>
    <td> Stands for Total Serious Injuries. Total number of people admitted to hospital with overnight stay as a result of a road crash</td>
  </tr>
<tr>
    <td> Total MI </td>
    <td> Stands for Total Minor Injuries. Total number of people treated by private doctor or treated at hospital but not admitted</td>
  </tr>
<tr>
    <td> Year </td>
    <td> Year of the crash</td>
  </tr>
<tr>
    <td> Month </td>
    <td> Month in which the accident took place</td>
  </tr>
<tr>
    <td> Day </td>
    <td> The day of the week the crash occurred </td>
  </tr>
<tr>
    <td> Time </td>
    <td> The reported time of the crash </td>
  </tr>
<tr>
    <td> Area Speed </td>
    <td> The speed limit at the time and location of the crash </td>
  </tr>
<tr>
    <td> Position Type </td>
    <td> Identifying if a crash location was at an intersection or midblock </td>
  </tr>
<tr>
    <td> Horizontal Align </td>
    <td> Defines the horizontal alignment of the road at the sight of the crash </td>
  </tr>
<tr>
    <td> Vertical Align </td>
    <td> Defines the vertical alignment of the road at the sight of the crash </td>
  </tr>
 <tr>
    <td> Other Feat </td>
    <td> Defines other relevant features of the crash site locations </td>
  </tr>
 <tr>
    <td> Road Surface </td>
    <td> Defines the road surface type at the crash location</td>
  </tr>
 <tr>
    <td> Moisture Cond </td>
    <td> Defines the pavement surface moisture condition at the crash location</td>
  </tr>  
<tr>
    <td> Weather Cond </td>
    <td> Defines the weather condition at the time and location of the crash </td>
  </tr>  
<tr>
    <td> DayNight </td>
    <td> The lighting condition at the time and location of the crash </td>
  </tr>  
<tr>
    <td> Crash Type </td>
    <td> Defines the road crash type </td>
  </tr>  
<tr>
    <td> Unit Resp </td>
    <td> The number of the unit determined to be responsible for the road crash </td>
  </tr>  
<tr>
    <td> Entity Code </td>
    <td> A code defining the entity deemed to be responsible for the road crash</td>
  </tr>  
<tr>
    <td> CSEF Severity </td>
    <td>Defines the road crash severity (classified by the highest injury severity sustained in the crash). Decoded values:“3: SI” = Serious Injury, “2: MI” = Minor Injury, “1: PDO”= Property Damage Only </td>
  </tr>  
<tr>
    <td> Traffic Ctrls </td>
    <td> Defines the traffic control at the time and location of the road crash </td>
  </tr>  
<tr>
    <td> DUI Involved </td>
    <td> Involved if at least one controller in the crash recorded an illegal Blood Alcohol Concentration level</td>
  </tr>  
<tr>
<tr>  
    <td> Drugs Involved </td>
    <td> Involved if at least one controller in the crash tested positive for a prescribed drug (THC (cannabis), methylamphetamine (speed, ice or crystal meth) or MDMA (ecstasy))</td>
  </tr>  
<tr> 
    <td> ACCLOC_X  </td>
    <td> The Y coordinate of the crash when located</td>
  </tr>  
<tr>
    <td> ACCLOC_Y</td>
    <td> The Y coordinate of the crash when located</td>
  </tr>  
<tr>
    <td> UNIQUE_LOC  </td>
    <td> A concatenation of the X and Y coordinates for the purpose of grouping crashes</td>
  </tr>  
</table>


#### 2.3 Data Cleaning

For the purpose of this report we have dropped the following columns on the data set: REPORT_ID, Postcode, LGA Name, Total Cas, Total Fats, Total SI, Total MI, Year, Month, Time, Horizontal Align, Vertical Align, Other Feat, Unit Resp, Entity Code, ACCLOC_X, ACCLOC_Y, UNIQUE_LOC. We have also combined both, DUI Involved and Drugs Involved columns will also be combined into a new column that will be named as 'Under Influence' and will be used to find the relationship between the use of substances and traffic crashes as well as its severity. 



### 3. Exploratory Data Analysis: 

#### 3.1 Data Exploratory Analysis and Processing

<b> DUI Involved and Drugs Involved</b>: the first variable I have worked was the substances. I merged both variables into one colunm called "Under Influence", in which:

0: Not under influence
1: Under the influence of either Alcohol or Other Substances
2: Under the influence of both Alcohol and Other Substances

After creating the new variable, both the DUI Involved and Drug Involved fields were dropped. 

<b> Area Speed </b> 

With the area speed I have plotted a BoxPlot graphic to determine how the increase in the area speed was related to the severity of accidents, and as expected the highest the speed, the higher the severity of an accident. 

<img src=data:image/png;base64,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>











<ol>
  <li>What are the most relevant elements that contribute to road accidents with causalities?</li>
  <li>Would the time of the day or day of the week influence when an accident happen?</li>
  <li>What about the road conditions? The fact of a road being sealed or unsealed influence in accidents severity?</li>
<li>Does rain impact on number of accidents?</li>
<li>In case of accidents involving abuse of substances such as alcohol or drugs - what is the impact on the severity of a crash?</li>
<li>Are there areas that require more attention do to higher concentration of accidents in the region? If so, what are the conditions in which accidents happen and what can we do to improve. ie. Reduce Speed Limit.</li>
</li>
</ol>

