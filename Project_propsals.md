#mta_eda
MTA Kids time [exploratory data analysis]

###Question/need:

The New York City Department of Education is planing to host annual sports competition for middle school students at Barclays Center. These games will be held over a period of 1 week in summer . As part of this, around 3000 students (participating and attending) need to use MTA as transport mechanism to the stadium.

## Purpose of the model/system:

Perform data analysis on the MTA turnstile data to:

1. Find out lowest entry volume for following stations per week for summer season( May to July):

  **The closest stations to Barclays Center are:**

    1. Atlantic Av/Flatbush Av is 97 yards away, 3 min walk.
    2. Flatbush Av/5 Av is 142 yards away, 3 min walk.
    3. Flatbush Av/Atlantic Av is 167 yards away, 3 min walk.
    4. Atlantic Av - Barclays Ctr [B,D,N,Q,R,2,3,4,5] is 211 yards away, 4 min walk.
    5. Dean St/5 Av is 236 yards away, 4 min walk.
    6. Atlantic Terminal is 242 yards away, 4 min walk.
    7. 5 Av/Bergen St is 244 yards away, 4 min walk.
    8. Fulton St [G] is 535 yards away, 7 min walk.
    9. Lafayette Av [A,C] is 542 yards away, 8 min walk.

  Note: The reason behind these selecting these stations is their proximity to Barclays center as metioned here.
  https://moovitapp.com/index/en/public_transit-Barclays_Center-NYCNJ-site_19034075-121

2. Suggest the best week to travel and the worst week to avoid travelling


This way kids can travel safely using MTA to attend the event.

*Benefits*:
1. This provides the most optimal time window for the kids and their families to travel using MTA.
2. Once the optimal time window has be determined, MTA can then plan additional security during the time slots throughout the transit system.

## Data Description

 Following is are the fields in MTA turnstile:
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
DIVISION = Represents the Line originally the station belonged to BMT, IRT, or IND  DATE     = Represents the date (MM-DD-YY)
TIME     = Represents the time (hh:mm:ss) for a scheduled audit event
DESc     = Represent the "REGULAR" scheduled audit event (Normally occurs every 4 hours)

ENTRIES  = The comulative entry register value for a device
EXIST    = The cumulative exit register value for a device

Details of the data:
- The readings occur every 4 hours
- The 4-hour observation windows are not the same for all turnstiles
- Each control area is in a “remote unit”. Remote unit generally represents a single station, but some stations and station complexes have several associated remote unit ids.
The Entries and exists are not count for given time but are [counters](https://copperegg.zendesk.com/hc/en-us/articles/214635123-Data-types-for-custom-metrics-gauges-vs-counters#:~:text=Counters%20%2D%20The%20Metrics%20whose%20value,to%20be%20of%20gauge%20type)