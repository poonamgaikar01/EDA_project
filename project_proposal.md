# Proposal #1:

The New York City Department of Education is planing to host annual competition for middle school students at Barclays Center. These games will be held over a period of 1 week. As part of this, around 5000 students (participating and attending) need to use MTA as transport mechanism to the stadium.

## Purpose of the model/system:

Perform data analysis on the MTA turnstile data to:

1. Find out lowest entry volume by station per day for last two years (is 2 year feasible?)
2. Suggest the best week to travel and the worst week to avoid travelling


This way kids can travel safely using MTA to attend the event.

*Benefits*:
1. This provides the most optimal time window for the kids and their families to travel using MTA.
2. Once the optimal time window has be determined, MTA can then plan additional security during the time slots throughout the transit system.



# Proposal #2:

COVID has a deep impact on various businesses. One of the industry most impacted was restaurant. As business are now recovering, one of the restaurant chain is looking to setup new restaurants across New York.Panadamic has changed MTA traffic pattern. Thus the restaurant chain is looking for recommendation for location to setup new outlets.

## Purpose of the model/system:

Perform data analysis on the MTA turnstile data to:

1. Find out highest entry volume by station by day.
2. Suggesttop 10 stations suitable for restaurant location.


*Benefits*:

1. Restaurant chain will use this data to plan for setting up the restaurants.
2. They also plan to use data around neighborhoods most impacted by COVID. Neighboorhoods with most impact and with good traffic will be the optimun once to setup the restaurant.


# Data Description

1. We plan to use the MTA turnstile data and dataset showing job loss by neighborhood (for second idea. Is this available?)
2. Following is are the fields in MTA turnstile:


`
C/A,UNIT,SCP,STATION,LINENAME,DIVISION,DATE,TIME,DESC,ENTRIES,EXITS
`

Below is the description of each field:

C/A      = Control Area (A002)

UNIT     = Remote Unit for a station (R051)

SCP      = Subunit Channel Position represents an specific address for a device (02-00-00). This is the turnstile unique with a Control Area / Unit.

STATION  = Represents the station name the device is located at

LINENAME = Represents all train lines that can be boarded at this station
           Normally lines are represented by one character.  LINENAME 456NQR repersents train server for 4, 5, 6, N, Q, and R trains.

DIVISION = Represents the Line originally the station belonged to BMT, IRT, or IND  
DATE     = Represents the date (MM-DD-YY)

TIME     = Represents the time (hh:mm:ss) for a scheduled audit event

DESc     = Represent the "REGULAR" scheduled audit event (Normally occurs every 4 hours)

1. Audits may occur more that 4 hours due to planning, or troubleshooting activities.
2. Additionally, there may be a "RECOVR AUD" entry: This refers to a missed audit that was recovered.

ENTRIES  = The comulative entry register value for a device

EXIST    = The cumulative exit register value for a device


Details of the data:

- The readings occur every 4 hours
- The 4-hour observation windows are not the same for all turnstiles
- Each control area is in a “remote unit”. Remote unit generally represents a single station, but some stations and station complexes have several associated remote unit ids.
The Entries and exists are not count for given time but are [counters](https://copperegg.zendesk.com/hc/en-us/articles/214635123-Data-types-for-custom-metrics-gauges-vs-counters#:~:text=Counters%20%2D%20The%20Metrics%20whose%20value,to%20be%20of%20gauge%20type)