# Regatta Data information

There is a number of file formats that were originally created by FinishLynx and have become standard file formats. Unfortunately there is not a lot of information available on these formats. I find myself searching for the same information and then not finding it :) Will keep it all in this repo

## FinishLynx results format (.LIF)

The LIF format is poorly described in this [page](https://finishlynx.com/file-formats-meet-manager/ "page"). Information from multiple sources was used to reproduce the below definition.

FinishLynx generates a LIF file per event. Their suggested naming convention is \<event name>.lif

### Header line
The first line in the file provides some summary information on the event that the results are for.

`Event Number | Round Number | Heat Number | Event Name | Wind | Wind Units | Template File | ? | ? | Distance | Start Time`

This file is in CSV format, each "|" symbol is replaced by a CSV in the final output file.

|  Field | Description   |
| :------------ | :------------ |
|  Event Number | Event Number: Event number assigned by Meet Management software. Also found in .evt file. Each event has a unique ID.  |
|  Round Number | Round Number: Round number assigned by Meet Managment software. Also found in .evt file. Imagine time trials vs. finals  |
|  Heat Number | Heat Number: Heat number assigned to the round for this event assigned by Meet Managment software. Also found in .evt file.  |
|  Event Name |  Event Name: Name of the the event, created in Meet Management software. Also found in .evt file. |
|  Wind |  Not used in rowing |
|  Wind Units | Not used in rowing  |
|  Template File |  Unknown |
|  ?  | Unknown  |
|  ? |  Unknown |
|  Distance |  Distance of the event in meters |
| Start Time | Start time in HH:MM:SS.mmm |

### Result lines
Each following line contains a single result

`Place, ID, lane, last name, first name, affiliation, <time>, license, <delta time>, <ReacTime>, <splits>, time trial start time, user 1, user 2, user 3`

|  Field | Description   |
| :------------ | :------------ |
|Place|Place of the participant in finishing the race|
|ID|ID of the Racer, assigned by Meet Managment software (could be a bib number). Can be found in the .evt file|
|lane|For sprint races, the lane number. For time trials, the bow number|
|last name|Last name|
|first name|First name|
|affiliation|Club name|
|\<time>|Finish time in HH:MM:SS.mmm|
|license|Not used in rowing|
|\<delta time>|Time difference from last crew to current crew. Crew in first place will have their finish time value here. Time in HH:MM:SS.mmm|
|\<ReacTime>|Now used in rowing|
|\<splits>| Unknown|
|time trial start time| Time of day timestamp for start of time trial|
|user 1|Unknown|
|user 2|Unknown|
|user 3|Unknown|
