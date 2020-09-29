# Business Case: Predicting the Severity of Crashes in South Australia To Reduce the Number of Accidents and Better Allocate Resources


### Introduction and Business Problem

According to the WHO (World Health Organization), approximately 1.35 million people die each year victim of road accidents, with another 20+ million people suffering some kind of non-fatal injury from traffic crashes. Road traffic injuries are also the leading cause of death for children and young adults aged 5-29 years old, making it a problem to governments all over the world. Road traffic injuries can cause considerable economic losses to families and individuals and cost to most countries around 3% of their gross domestic product. 

During 2019, from January to December, South Australia has seen 12,964 accidents with 114 fatalities and 6031 casualities, and both crashes and injuries can be prevented using data to predict the variables that influence on accidents, and making a different approach to effective improve the allocation of resources such as traffic controllers and policy to locations that are at a higher risk of accidents, improving transport and roads planning, raising public awareness about risks of crashes, and identifying risk factors to reduce number of accident and create a more secure environment and saving lives.

Some of the questions that will be addressed in my model will include:

<ol>
  <li>What are the most relevant elements that contribute to road accidents?</li>
  <li>Would the time of the day or day of the week influence when an accident happen?</li>
  <li>What about the road conditions? The fact of a road being sealed or unsealed influence in accidents severity?</li>
<li>Does rain impact on number of accidents?</li>
<li>In case of accidents involving abuse of substances such as alcohol or drugs - what is the impact on the severity of a crash?</li>
<li>Are there areas that require more attention do to higher concentration of accidents in the region? If so, what are the conditions in which accidents happen and what can we do to improve. ie. Reduce Speed Limit.</li>
<li>Based on day of the week and location, how can we better allocate resources such as traffic controllers and police to a region to reduce risks of accident?</li>
</ol>

Audience / Client: Government of South Australia and Australian Government - If a formula is found to improve the allocation of resources and reduce the burden on the economy caused by traffic crashes, the money saved on costs related to crashes can be reallocated into other structural projects and improvements, saving the country and State not only on the budget but also saving the lives of its citizens. 

### Data Set Information

Open Source: https://www.dpti.sa.gov.au/

Data Set: The data set include information on crashes that happened in South Australia during 2019 including details on type of crash, number or units involved on the accident, if the person causing the accident was under influencing, the day of the week, time, type of road, weather conditions, speed limit on the area, traffic control conditions and severity of the crash (including mention to causualities and fatalities).

Data Model Approach: After cleaning the data, I will create a decision tree model to predict the severity of an accident using multiple variables.

Data Set Info:


The data set has 12965 rowns and 33 columns, including headers. More information on the data below: 

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
    <td> The Local Government Area that the crash occurred in. This piece of information will be dropped during the data cleaning process</td>
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
    <td> Year of the crash. This column will be dropped for analysis purposes, as all accidents reported on the data set happened in 2019</td>
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
    <td> Defines the horizontal alignment of the road at the sight of the crash. We will drop this column for the purposes of this study</td>
    <td> 12964 </td>
  </tr>
<tr>
    <td> Vertical Align </td>
    <td> Defines the vertical alignment of the road at the sight of the crash. We will drop this column for the purposes of this study</td>
    <td> 12964 </td>
  </tr>
 <tr>
    <td> Other Feat </td>
    <td> Defines other relevant features of the crash site locations. We will drop this column for the purposes of this study</td>
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
    <td> Involved if at least one controller in the crash recorded an illegal Blood Alcohol Concentration level. I will combine both DUI and Drugs into a column for under the influence to facilitate the study</td>
    <td> 349 </td>
  </tr>  
<tr>
<tr>  
    <td> Drugs Involved </td>
    <td> Involved if at least one controller in the crash tested positive for a prescribed drug (THC (cannabis), methylamphetamine (speed, ice or crystal meth) or MDMA (ecstasy)). I will combine both DUI and Drugs into a column for under the influence to facilitate the study </td>
    <td> 314 </td>
  </tr>  
<tr> 
    <td> ACCLOC_X  </td>
    <td> The Y coordinate of the crash when located.  I will drop this column for the study </td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> ACCLOC_Y</td>
    <td> The Y coordinate of the crash when located.  I will drop this column for the study</td>
    <td> 12964 </td>
  </tr>  
<tr>
    <td> UNIQUE_LOC  </td>
    <td> A concatenation of the X and Y coordinates for the purpose of grouping crashes. I won't use this column in the study, as I will try to group per suburbs </td>
    <td> 12964 </td>
  </tr>  
</table>


