# Requirements

## Functional requirements (what the system must DO)

- **FR1:** The system shall fetch new satellite hotspot data automatically every 10 minutes
- **FR2:** The system shall keep only hotspots located in Sarawak and in West and Central Kalimantan.
- **FR3:** The system shall classify each hotspot as a persistent fire or a short-lived detection
- **FR4:** The system shall predict for each selected Sarawak monitoring station, whether the API will exceed 100 the next day
- **FR5:** The system shall rank hotspots from highest to lowest haze risk to Sarawak, using each hotspot's class, fire strength, distance and wind direction.
- **FR6:** The system shall display the hotspots on a map coloured by class, together with the ranked list and the next-day forecast.
- **FR7:** The system shall show the time the satellite data was captured and the time of the last update.
- **FR8:** The system shall replay an archived haze episode and report its precision, recall and F1-score.

## Non-functional requirements (how the system must PERFORM)

- **NFR1:** The system shall complete each update within 5 minutes of new satellite data arriving.
- **NFR2:** The system shall classify hotspots with an F1-score of at least 0.80 when tested on data not used for training, using the August–September 2026 haze episode.
- **NFR3:** The system shall correctly forecast at least 75% of unhealthy days (API above 100) when tested on the August–September 2026 haze episode.
- **NFR4:** The system shall run unattended for at least 7 days without a manual restart.
