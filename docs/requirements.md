# Requirements

## Functional requirements

| ID  | Requirement                                                                                                   |
| --- | ------------------------------------------------------------------------------------------------------------- |
| FR1 | The system shall display satellite fire hotspots for Sarawak and West and Central Kalimantan on a map.        |
| FR2 | The system shall classify each hotspot as a persistent fire or a short-lived detection.                       |
| FR3 | The system shall rank hotspots by haze-risk score, highest first.                                             |
| FR4 | The system shall show, for each selected Sarawak station, whether the next-day API is forecast to exceed 100. |
| FR5 | The system shall show hotspots within a user-chosen distance of the user's GPS location.                      |
| FR6 | The system shall refresh hotspot data automatically when new satellite data is released.                      |
| FR7 | The system shall show the time of the last data update.                                                       |
| FR8 | The system shall open with the last saved results when there is no internet connection.                       |

## Non-functional requirements

| ID   | Type          | Requirement (measurable)                                                                                                                                         |
| ---- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| NFR1 | Performance   | The map and ranked list shall load in under 3 seconds on a 4G connection.                                                                                        |
| NFR2 | Timeliness    | The dashboard shall update within 5 minutes after each new satellite data release.                                                                               |
| NFR3 | Accuracy      | On the test data, the hotspot classifier shall reach an F1-score of at least 0.80, and the forecast shall detect at least 75% of unhealthy days (recall ≥ 0.75). |
| NFR4 | Usability     | At least 80% of test users shall find the ranked list within 1 minute without help.                                                                              |
| NFR5 | Security      | All data traffic shall use HTTPS, and no API key shall be stored in the repository.                                                                              |
| NFR6 | Compatibility | The app shall run on both Android and iOS.                                                                                                                       |

Note: the numbers in NFR1, NFR3 and NFR4 are project targets. They will be tested and the results reported honestly.

## Update (25 October 2026)

After supervisor feedback, the project changed from a web dashboard to a mobile app, with new objectives. The requirements were revised to FR1 to FR8 and NFR1 to NFR6, and the user stories were reduced to three (US1 to US3), each linked to a requirement and with acceptance criteria. The Sprint 1 entries above describe the work as it was done in Week 3.
