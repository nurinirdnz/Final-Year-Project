# AI-Based Real-Time Classification and Prioritisation of Fire Hotspots for Transboundary Haze Risk in Sarawak

This project helps Sarawak's environment and disaster agencies see which fire hotspots, in Sarawak and neighbouring Kalimantan, are most likely to cause haze, so they can warn the public before the smoke arrives.

## 1. Introduction

Transboundary haze is a recurring environmental and health problem in Sarawak, caused mainly by land and peat fires in neighbouring Kalimantan. Satellites already detect these fires as hotspots, but they report every hotspot the same way, with no indication of which ones threaten Sarawak's air. This project develops a near real-time AI system that classifies fire hotspots, predicts next-day haze in Sarawak, and ranks hotspots by their transboundary haze risk, so that agencies can act before the smoke arrives.

## 2. Background of Study

- **Haze in Sarawak:** In late August 2026, Sarawak recorded its worst air quality since 2019. One station reached an Air Pollutant Index (API) of 475, close to the level of 500 at which an emergency declaration is considered (Lu, 2026).
- **Where the smoke comes from:** On 30 August 2026, 1,180 hotspots were detected in Kalimantan in a single day (Malay Mail, 2026). In 2019, Sarawak's Department of Environment linked Sri Aman's air quality to wind direction and Kalimantan hotspots (Bernama, 2019).
- **Health impact:** The 2015 haze was estimated to have caused about 100,300 excess deaths across Indonesia, Malaysia and Singapore (Koplitz et al., 2016).
- **How fires are monitored:** NASA's VIIRS satellites detect fires at 375 m detail, published within about 3 hours of each satellite pass (Davies et al., 2024). Japan's Himawari-9 satellite scans the region every 10 minutes, with infrared detail of 1 to 2 km (Japan Meteorological Agency, n.d.).
- **AI in this field:** Machine learning has been used to predict peatland fire occurrence (Rosadi et al., 2020), predict fire activity in Southeast Asia (Eaturu & Vadrevu, 2025) and estimate air quality in Malaysia (Zaman et al., 2021), but these have not been combined for Sarawak.

## 3. Problem Statement

Hundreds of fire hotspots are detected daily across Sarawak and Kalimantan, but each appears as an identical point on a map (Malay Mail, 2026). Agencies have no automated way to separate lasting fires from brief detections, or to link them to Sarawak's air quality. As a result, haze is confirmed only after it arrives, as in August 2026 when one station reached API 475 (Lu, 2026). This leaves little time to warn the public and direct the response, putting people's health at risk.

## 4. Project Questions

1. How can machine learning classify satellite fire hotspots as persistent fires or short-lived detections, and predict next-day haze at Sarawak monitoring stations?
2. How accurately do the models perform on data not used for training, using the August–September 2026 haze episode, and does using only persistent hotspots predict haze better than using all hotspots?
3. Can the models be deployed in a dashboard that ranks hotspots by haze risk and updates within 5 minutes of new satellite data?

## 5. Project Objectives

1. To develop a hotspot classification model (persistent fire or short-lived detection) and a next-day haze prediction model using machine learning, trained on archived satellite hotspot, wind and Department of Environment API data from past Sarawak haze seasons, by Week 19.
2. To evaluate both models on data not used for training, using the August–September 2026 haze episode, targeting an F1-score of at least 0.80 for classification and a recall of at least 0.75 for predicting unhealthy days (API above 100), and to compare prediction using persistent hotspots against using all hotspots, by Week 23.
3. To deploy both models in a dashboard that ranks hotspots by haze risk to Sarawak and updates automatically within 5 minutes of each new satellite data release, by Week 26.

## 6. Project Scope

| Aspect     | In scope                                                                                                                      |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Area       | Hotspots in Sarawak and in West and Central Kalimantan. Haze prediction at two to three Sarawak monitoring stations.          |
| Data       | Satellite hotspots (Himawari-9 and NASA VIIRS), wind data, and Department of Environment API readings from past haze seasons. |
| Techniques | Machine learning for classification and prediction, and a rule-based risk score for ranking.                                  |
| Output     | A web dashboard with a hotspot map, a next-day haze forecast and a ranked hotspot list.                                       |
| Users      | Environment and disaster agencies, and fire and rescue teams.                                                                 |

**Not included:** detecting fires from raw satellite images, firefighting operations, regions outside Sarawak and Kalimantan, and a validated ranking of individual fires.

## 7. Significance of Study

- **For agencies:** a next-day haze warning for Sarawak, before the smoke arrives.
- **For fire and rescue teams:** the most dangerous fires listed first, so effort goes where it matters most.
- **For the public:** more time to prepare, for example by closing schools or protecting vulnerable people.
- **For research:** among the studies reviewed, the first to combine hotspot classification with haze prediction for Sarawak.

## 8. Conclusion

This project addresses a gap in current hotspot monitoring: hotspots are detected, but they are not classified or linked to haze risk in Sarawak. It sets out three project questions and three objectives: to develop the models, to evaluate them, and to deploy them in a near real-time dashboard. Its scope is limited to Sarawak and the neighbouring part of Kalimantan, and its main value is giving agencies earlier warning of which fires matter.

## Documents

- [Problem statement](docs/problem-statement.md)
- [Requirements](docs/requirements.md)
- [User stories](docs/user-stories.md)

## Author

Nurin Irdina Safiah binti Arif Sarjana (for Final Year Project)

## References

- Bernama. (2019, September 20). _Wind direction, hotspots in Kalimantan cause higher API in Sri Aman_. Malay Mail. https://www.malaymail.com/news/malaysia/2019/09/20/wind-direction-hotspots-in-kalimantan-cause-higher-api-in-sri-aman/1792663
- Davies, D., Hewson, J., & Olsina, O. (2024, September). _NASA's Fire Information for Resource Management System (FIRMS)_ [Conference presentation]. GOFC-GOLD Fire. https://gofcgold.umd.edu/sites/default/files/2024-11/DAVIES%20_%20FIRMS%20GOFC-FIRE%20September%2024.pdf
- Eaturu, A., & Vadrevu, K. P. (2025). Evaluation of machine learning and deep learning algorithms for fire prediction in Southeast Asia. _Scientific Reports, 15_, 18807. https://doi.org/10.1038/s41598-025-00628-9
- Japan Meteorological Agency. (n.d.). _Outline of Himawari-8/9_. https://www.jma.go.jp/jma/jma-eng/satellite/himawari89.html
- Koplitz, S. N., Mickley, L. J., Marlier, M. E., Buonocore, J. J., Kim, P. S., Liu, T., Sulprizio, M. P., DeFries, R. S., Jacob, D. J., Schwartz, J., Pongsiri, M., & Myers, S. S. (2016). Public health impacts of the severe haze in Equatorial Asia in September–October 2015: Demonstration of a new framework for informing fire management strategies to reduce downwind smoke exposure. _Environmental Research Letters, 11_(9), 094023. https://doi.org/10.1088/1748-9326/11/9/094023
- Lu, W. H. (2026, September 1). _Malaysia's Sarawak nears haze emergency as air quality hits worst level since 2019_. The Straits Times, via Asia News Network. https://asianews.network/malaysias-sarawak-nears-haze-emergency-as-air-quality-hits-worst-level-since-2019/
- Malay Mail. (2026, August 30). _DOE: Transboundary haze thickens, 1,211 hotspots detected in southern Asean, mostly in Kalimantan_. https://malaymail.com/news/malaysia/2026/08/30/doe-transboundary-haze-thickens-1211-hotspots-detected-in-southern-asean-mostly-in-kalimantan/233272
- Rosadi, D., Andriyani, W., Arisanty, D., & Agustina, D. (2020). Prediction of forest fire occurrence in peatlands using machine learning approaches. In _2020 3rd International Seminar on Research of Information Technology and Intelligent Systems (ISRITI)_ (pp. 48–51). https://ir.lib.ugm.ac.id/id/eprint/22056/
- Zaman, N. A. F. K., Kanniah, K. D., Kaskaoutis, D. G., & Latif, M. T. (2021). Evaluation of machine learning models for estimating PM2.5 concentrations across Malaysia. _Applied Sciences, 11_(16), 7326. https://doi.org/10.3390/app11167326
