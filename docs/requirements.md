# Requirements

## Functional requirements (what the system must DO)
1. The system shall fetch new satellite hotspot data automatically every 10 minutes.
2. The system shall keep only hotspots located in Sarawak and in West and Central Kalimantan.
3. The system shall classify each hotspot as a persistent fire or a short-lived detection.
4. The system shall predict, for each selected Sarawak monitoring station, whether the API will exceed 100 the next day.
5. The system shall rank hotspots from highest to lowest haze risk to Sarawak, using each hotspot's class, fire strength, distance and wind direction.
6. The system shall display the hotspots on a map coloured by class, together with the ranked list and the next-day forecast.
7. The system shall show the time the satellite data was captured and the time of the last update.
8. The system shall replay an archived haze episode and report its precision, recall and F1-score.

## Non-functional requirements (how the system must PERFORM)
1. The system shall complete each update within 5 minutes of new satellite data arriving.
2. The system shall classify hotspots with an F1-score of at least 0.80 when tested on data not used for training, using the August–September 2026 haze episode.
3. The system shall correctly forecast at least 75% of unhealthy days (API above 100) when tested on the August–September 2026 haze episode.
4. The system shall run unattended for at least 7 days without a manual restart.
