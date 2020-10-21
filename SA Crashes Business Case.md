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

<b> DUI Involved and Drugs Involved</b>

The first variable I have worked was the substances. I merged both variables into one colunm called "Under Influence", in which:
<ul>
  <li>0: Not under influence</li>
  <li>1: Under the influence of either Alcohol or Other Substances</li>
  <li>2: Under the influence of both Alcohol and Other Substances</li>
 </ul>

After creating the new variable, both the DUI Involved and Drug Involved fields were dropped. I have also checked on how driving under the influence of substances relates to the severity of accidents, and the results indicates that fatalities happen in 0.06% of the cases in which no substance consumption is involved, increasing to 4% when at least one substance (either alcohol or drugs) is consumed, and 18% when both alcohol and drugs have been consumed. 

<img src="https://1drv.ms/u/s!Atcy32bbrRg24CIzmjtQE1BFn8aC?e=fhJJu1" alt="CSEF Severity vs Under Influence">

While still working with this variable, I have also identified that accidents that happen during the weekend have more chances of having conductors under the influence of substance, in opposite to accidents happening early and mid-week. 

<img src="https://1drv.ms/u/s!Atcy32bbrRg24CBeJR05jfzXaPKi?e=GI9M8f" alt="Day vs Under Influence">

<b> Area Speed </b> 

With the area speed I have plotted a BoxPlot graphic to determine how the increase in the area speed was related to the severity of accidents, and as expected the highest the speed, the higher the severity of an accident. 

<img src="https://1drv.ms/u/s!Atcy32bbrRg24CPpAGQB92b8iwaG?e=77NiGS" alt="Area Speed vs CSEF Severity">

<b> Road Surface, Moisture Cond, Traffic Ctrls, Crash Type</b>

After evaluating those variables, none of them were identified as having a strong correlation to the severity of accidents, therefore we dropped them from our analysis. 

<b> DayNight & Weather Cond</b>

Although, also not showing a strong correlation to the severity of accidents, we have processed and kept both variables for the model. 

<b> Total Units </b>

I have used a boxplot to observe if the number of units involved on a crash would be related with the severity of injuries, and identified that most accidents that have fatalities involve 2 or 3 units, therefore I have dropped all other data entries containing less than 2 and more than 3 vehicles. 

<img src="https://1drv.ms/u/s!Atcy32bbrRg24CEw_-ZB-4THXadk?e=yXSxUR" alt="Total Units vs CSEF Severity">

<b> Area and Suburb </b>

Again there are not strong correlation on the severity of crashes and the area in which occurs. With fatalities reported if accidents happenend in the city sitting at 0.1%, Metropolitan Region at 0.4% and Country at 0.3%. I have processed the data to convert it to an integer, with the following code: 
<ul>
  <li>1: City</li>
  <li>2: Metropolitan</li>
  <li>3: Country</li>
 </ul>

For the sole purpose of this project and to facilitate the data analysis, I have dropped the Suburb in which the accidents have occurred, but I will address my recommendation to this variable later in this case study. 

<b> Unknown values </b>

I have analysed every single one of the variables, and any of them containing values showing 'Unknown' have been discarded during the data cleaning/prossing process. 


#### 3.2 Questions 

<ul>
  <li>What are the variables close related to the severity of injured victims from road accidents?</li>
  <li>Are accidents involving abuse of substances such as alcohol or drugs - what is the impact on the severity of a crash?</li>
  <li>Are there areas that require more attention from traffic controllers due to a higher number of accidents involving more severe injuries or fatalities? </li>
  <li>What are the initiatives that in theory could support the reduction of accidents and potentially drive a ZERO Fatality rate from Crashes in SA?</li>
</ul>


### 4. Model:

#### 4.1 The Decision Tree

Decision Trees are models schematically presented in the structure of a tree and as a rle, it starts with a root node and branches into variable possible outcomes. 
A decision tree in the case of Severity of Accidents would help the SA government determine things such as when to allocate additional emergency services to an area or deploy additional traffic controllers to the city/metropolitan regions/ country locations. 

#### 4.2 The Modelling Process

<b>Define X and Y </b>

<ul>
  <li> Step 1: I have set up a new dataframe called <i> Feature </i> using the following variables: Stats Area, Total Units, Day, Area Speed, Weather Cond, DayNight, Under Influence. During this process, in the code, I have also used the pd.getdummies function to Transform the Position Type variable into an integer.</li>
  <li> Step 2: I have defined X using the Feature Dataframe. </li>
  <li> Step 3: I have defined Y with the CSEF Severity variable. </li>
  <li> Step 4: I have normalized X. </li>
  <li> Step 5: I split the data into <i>Sample</i> and <i>Training</i>. Using 30% of the data to test and the remaining 70% to train the model.</li> 
  <li> Step 6: I used the X_DTTrain and Y_DTTrain to train and fit my decision tree model.</li>
  <li> Step 7: I used my Y_DTTest data to check the accuracy of the model and predict the severity of crashes.</li>
 </ul>
 
 <strong> Note! </strong> All code is available on the Watson's Notebook submitted in the Coursera_Capstone Repository under the name Coursera_Capstone_Final.ipynb.
 
 #### 4.2 Decision Tree Accuracy
 
 The Jaccard Similary / Metrics for Accuracy shows that the Prediction Tree on the test set would return a correct prediction in 64% of the cases. The F1-Score weighted predicts that the accuracy of the model is of 53%.
 
 In order to determine the accuracy, all metrics functions/libraries were downloaded and coded for the purpose.
 
 
 ### 5. Conclusion
 
 It was clear during the data cleaning process that the two main variables influencing the severity of injured people on accidents were driving under influence of alcohol or other substances, and the speed recorded in the area and at the time the accident happened. After analysing all other variables, none of them including the Area Stats, Pavement Conditions or Weather Condition have a strong correlation to the severity of crashes, with percentage values showing very close results for other variables. 
  
Accidents involving substances have higher chances in resulting on a fatality or serious injury, with the respective results: Only 4.6% of accidents in which the driver has not consumed any substances results in a serious injury or a fatality, while this number increases to 21.4% when the responsible for the accident is driving under the influence of alcohol and an staggering 44.1% when both alcohol and other drugs are combining. Showing driving under any influence is a major determinant for the severity of accidents. 

There was not a strong correlation on the area in which accidents occur or the presence of traffic controls in the severity of the accidents. 

The decision tree model did not have a high accuracy due to the number of variables that did not have a strong correlation with accident severity, but, from the data analysis I have the following suggestions on initiatives that could support the reduction of accidents in SA: 

<ul>
  <li><b>Emergency Services Staff:</b> Ensure that in the days of the week when the consumption of substances is increased - Sunday, Saturday and Thursday respectively, emergency response cars and paramedics, as well as public hospital staff are present in a higher number. Sometimes, the time that takes to treat an injured person would make the difference between life and death.</li>
  <li><b>Speed Cameras in All Areas with Speed Limit 80Km and HigherL</b> Since the speed correlates with the accident severity, installing speed cameras in all locations with speed limits 80Km or higher would actually ensure that the speed in the zone is respected, in most circumstances, what could potentially lead to a reduction on serious injuries or fatalities from accidents. This action would require budget allocation and spending by the State government, but in the long run it would pay itself.</li>
  <li><b>Police Blitz in Areas With Speed Limit between 60Km and 80Km:</b> Ensure police personal is allocated to areas with speed limit between 60 and 80 Km, specially on days with high incidence of substance consumption. The police blitz can do random checks, but also stop cars that could potentially be involved in an accident.</li>
  <li><b> State Based Marketing Campaign About Injuries, Substance Abuse and Respect of the Traffic Rules (Inc. Speed Limit):</b> Allocate budget for a State based marketing campaign, utilizing different medias such as Outdoors, Vehicle Decal, TV, Radio and Flyers to educate the population on the risks of not respecting traffic rules such as the speed limit or consume substances and drive.</li>
 </ul>
 
 
 ### 6. Future Directions
 
 As mentioned the model accuracy in this occasion is not ideal, due to the lack of correlated variables and the severity of accident. Future directions, including more data collection and combining variables from other sources from the government, such as gender, age and cases in which the patients enter an hospital as a serious injury and end up becoming a fatality. 
 
 The model needs to keep being refit for improved performance, and tests conduced if any of the suggestions to reduce the severity of the accidents has created a positive impact. 
 
 An additional suggestion to fit a more detailed model is creating maps to determine by suburb where the highest concentration of accidents happen and analyse also what is the severity of cases and not only number of accidents in those areas, and use this variable to improve further how personal and assets are allocated. 
