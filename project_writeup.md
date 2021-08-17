
## MTA LOW TRAFFIC WEEK FOR KIDS SAFE TRAVEL

## Abstract

For this project, my goal was to Establish best week to travel to Barclays Center via the 7 closest MTA stations. To do so, I built graphs and plots to analyze my findings.

MTA is the backbone of the New York Public transportation. Millions of people rely on it as their transportation mechanism.
Big public events often put more strain on the system which is already strained. New York school department is planning to host sports competition for middle school students at Barclays center. This will be held during the summer time. It is estimated that around 5000 students along with families will travel to Barclays center to attend the event.
They will most likely use MTA as the transport mechanism. The 7 closest stations within walking distance to Barclays center will be most likely be used by the student.

## Design

For this project, I used MTA turnstiles dataset for New York School department wants to establish a MTA ridership pattern for summer season for the 7 closest station to barclays center. In order to establish a pattern, goal is to analyze last 3 years worth of Turnstile data for summer.
The goal here is to establish the best week for the kids  to travel to barclays center via the 7 closest stations  
As this event will be held in 2022, this established week will be used by the New Yourk Schook Department to plan for additional security, transport etc.

## Data
MTA Turnstile data is collected approx every 4 hours. Which means that for each of the Turnstile there will be 6 entries. While the data is collected every 4 hours, it is made availalbe on the MTA website every week for the corresponding week. Following is are the fields in MTA turnstile:
C/A,UNIT,SCP,STATION,LINENAME,DIVISION,DATE,TIME,DESC,ENTRIES,EXITS

Below is the description of each field:

C/A = Control Area (A002)

UNIT = Remote Unit for a station (R051)

SCP = Subunit Channel Position represents an specific address for a device (02-00-00). This is the turnstile unique with a Control Area / Unit.

STATION = Represents the station name the device is located at

LINENAME = Represents all train lines that can be boarded at this station Normally lines are represented by one character. LINENAME 456NQR repersents train server for 4, 5, 6, N, Q, and R trains.

DIVISION = Represents the Line originally the station belonged to BMT, IRT, or IND
DATE = Represents the date (MM-DD-YY)

TIME = Represents the time (hh:mm:ss) for a scheduled audit event

DESc = Represent the "REGULAR" scheduled audit event (Normally occurs every 4 hours)

Audits may occur more that 4 hours due to planning, or troubleshooting activities.
Additionally, there may be a "RECOVR AUD" entry: This refers to a missed audit that was recovered.
ENTRIES = The comulative entry register value for a device

EXIST = The cumulative exit register value for a device

Each control area is in a “remote unit”. Remote unit generally represents a single station, but some stations and station complexes have several associated remote unit ids. The Entries and exists are not count for given time but are counters

Each turnstile can be identified by an unique combo of C/A, UNIT, SCP, STATION. 


## Algorithms

1. Collect MTA Turnstile data for 2018, 2019 and 2021 for summer season (May,June and July)
2. Filter this data only for the 7 closest stations:
  ATLANTIC AV,FLATBUSH AV-B.C,ATL AV-BARCLAY,25 AV,BERGEN ST,FULTON ST,LAFAYETTE AV 
3. Calculate daily volume per week only for weekdays.
4. Calculate total volumen by week number for the above data for each year.
5. Graph the data showing weekly volume (only for week days) for the past 3 years.
6. Establish the week which consistently has lowest volume for a given week.

###Findings

From this analysis, we can conclude that lowest entry volume for stations near by Barclays center during first week of June which is the week 22.
Thus, the best week to travel is first week of June. This way kids can travel safely using MTA to attend the event. During this time  MTA can plan additional security during the time slots throughout the transit system.


## Tools

Pandas for data manipulation
Matplotlib and Seaborn for plotting
Plotly for interactive visualizations
Geopandas for mapping visualizations

## Communication

A brief presentation slides on my exploration and analysis, and visuals. 