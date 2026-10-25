# AI-Based Real-Time Classification and Prioritisation of Fire Hotspots for Transboundary Haze Risk in Sarawak

![Views](https://komarev.com/ghpvc/?username=nurinirdnz-Final-Year-Project&label=Views&color=blue)

This project helps Sarawak's environment and disaster agencies, fire and rescue teams, and the public see which fire hotspots, in Sarawak and neighbouring Kalimantan, are most likely to cause haze, so they can be warned before the smoke arrives. It is delivered as a mobile app.

## 1. Introduction

Transboundary haze is a recurring environmental and health problem in Sarawak, caused mainly by land and peat fires in neighbouring Kalimantan. Satellites already detect these fires as hotspots, but they report every hotspot the same way, with no indication of which ones threaten Sarawak's air. This project develops a mobile app that processes satellite hotspot data in near real time. The app classifies hotspots as persistent fires or short-lived detections, predicts whether next-day air quality (API) will exceed 100 at selected Sarawak stations, and ranks hotspots by their transboundary haze risk, so that agencies and the public can act before the smoke arrives.

## 2. Background of Study

- **Haze in Sarawak:** In late August 2026, Sarawak recorded its worst air quality since 2019. One station reached an Air Pollutant Index (API) of 475, close to the level of 500 at which an emergency declaration is considered (Lu, 2026).
- **Where the smoke comes from:** On 30 August 2026, the Department of Environment reported 1,211 hotspots across southern ASEAN, mostly in Kalimantan (Malay Mail, 2026). In 2019, Sarawak's Department of Environment linked Sri Aman's air quality to wind direction and Kalimantan hotspots (Bernama, 2019).
- **Health impact:** The 2015 haze was estimated to have caused about 100,300 excess deaths across Indonesia, Malaysia and Singapore (Koplitz et al., 2016).
- **How fires are monitored:** NASA's VIIRS satellites detect fires at 375 m detail, published within about 3 hours of each satellite pass (Davies et al., 2024). Japan's Himawari-8/9 satellites scan the region every 10 minutes, with infrared detail of 1 to 2 km (Japan Meteorological Agency, n.d.).
- **AI in this field:** Machine learning has been used to predict peatland fire occurrence (Rosadi et al., 2020), predict fire activity in Southeast Asia (Eaturu & Vadrevu, 2025) and estimate air quality in Malaysia (Zaman et al., 2021), but these have not been combined for Sarawak.

## 3. Problem Statement

Satellites can tell agencies where fires are burning, but not which fires matter to Sarawak. Three problems get in the way:

1. **Every hotspot looks the same.** More than a thousand hotspots can appear across the region on a bad day (Malay Mail, 2026), each as an identical point on a map. Many are brief detections rather than lasting fires, and no automated method separates them.
2. **Existing forecasts do not use hotspot data.** The next-day forecasts reviewed rely on pollutant and weather readings only, and none ranks hotspots.
3. **Haze is confirmed only after it arrives,** as in August 2026 when one station reached API 475 (Lu, 2026). This leaves little time to warn the public and direct the response, putting people's health at risk.

## 4. Research Questions

1. Which machine learning model is best at classifying hotspots as persistent fires or short-lived detections and at predicting next-day haze in Sarawak?
2. How can the identified model be used in a mobile app with a dashboard that ranks hotspots by haze risk?
3. How well does the app work for its users, according to user testing with a questionnaire?

_(Draft, to be confirmed with the supervisor.)_

## 5. Project Objectives

1. To identify the best machine learning model for classifying hotspots and predicting next-day haze.
2. To develop a mobile app with a dashboard that uses the identified model to rank hotspots by haze risk.
3. To evaluate the app through user testing with a questionnaire.

## 6. Project Scope

| Aspect     | In scope                                                                                                                                                                                   |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Area       | Hotspots in Sarawak and in West and Central Kalimantan. Haze prediction at two to three Sarawak monitoring stations.                                                                       |
| Data       | Satellite hotspots (Himawari-8/9 and NASA VIIRS), wind data, and Department of Environment API readings from past haze seasons.                                                            |
| Techniques | Candidate machine learning models (for example random forest and XGBoost) compared on data not used for training (August–September 2026 episode), and a rule-based risk score for ranking. |
| Output     | A mobile app (Android and iPhone) with a dashboard: hotspot map, next-day haze forecast, ranked hotspot list, and GPS to show hotspots near the user.                                      |
| Timing     | Near real time: each update within 5 minutes of new satellite data; the data itself is delayed by about 10 minutes (Himawari-8/9) to 3 hours (VIIRS).                                      |
| Users      | Environment and disaster agencies, fire and rescue teams, and the public, including schools and families.                                                                                  |

**Not included:** detecting fires from raw satellite images, firefighting operations, regions outside Sarawak and Kalimantan, each fire's exact share of the haze, and a validated ranking of individual fires.

## 7. Significance of Study

- **For agencies:** a next-day haze warning for Sarawak, before the smoke arrives.
- **For fire and rescue teams:** the most dangerous fires listed first, so effort goes where it matters most.
- **For the public:** more time to prepare, for example by closing schools or protecting vulnerable people.
- **For research:** among the studies reviewed, the first to combine hotspot classification with haze prediction for Sarawak.

## 8. Conclusion

This project addresses a gap in current hotspot monitoring: hotspots are detected, but they are not classified or linked to haze risk in Sarawak. It sets out three research questions and three objectives: to identify the best model, to develop a mobile app that uses it, and to evaluate the app with users. Its scope is limited to Sarawak and the neighbouring part of Kalimantan, and its main value is giving agencies and the public earlier warning of which fires matter.

## Technology Used

The tools below are planned for the project and may change as development progresses.

| Area                           | Technology                                                       | Purpose                                                                                 |
| ------------------------------ | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Programming language           | Python, TypeScript                                               | Data processing and model training (Python); mobile app (TypeScript)                    |
| Data handling                  | pandas, NumPy                                                    | Cleaning and joining hotspot, wind and air quality data                                 |
| Machine learning               | scikit-learn, XGBoost, MLflow                                    | Comparing models, hotspot classification and next-day haze prediction, tracking results |
| Back end                       | FastAPI, Docker                                                  | Serving the chosen model to the app                                                     |
| Database and cache             | PostgreSQL/PostGIS, Redis                                        | Storing hotspots and caching results                                                    |
| Mobile app                     | React Native with Expo                                           | Mobile app for Android and iPhone                                                       |
| Map and location               | MapLibre React Native, expo-location                             | Interactive hotspot map and GPS                                                         |
| Scheduling                     | Python scheduler (for example, APScheduler)                      | Fetching new satellite data automatically                                               |
| Live hotspot data              | Himawari-8/9 wildfire product (JAXA P-Tree)                      | Fire detections every 10 minutes                                                        |
| Confirmation and training data | NASA FIRMS (VIIRS 375 m)                                         | Detailed fire detections and training labels                                            |
| Wind data                      | ERA5 reanalysis (Copernicus); weather forecast feed for live use | Wind speed and direction                                                                |
| Air quality data               | Department of Environment Malaysia (APIMS)                       | API readings used to train and test the predictor                                       |
| Version control and planning   | Git, GitHub, GitHub Actions, GitHub Projects                     | Code history, tests, issues and sprint board                                            |

## Documents

- [Problem statement, research questions, objectives and scope](docs/problem-statement.md)
- [Requirements](docs/requirements.md)
- [User stories](docs/user-stories.md)
- [Sprint log](docs/sprint-log.md)

## Project structure

```text
.
|-- README.md                  Project overview
|-- .gitignore                 Files Git must not track
|-- docs/
|   |-- problem-statement.md   Problem, research questions, objectives, scope and evidence
|   |-- requirements.md        Functional and non-functional requirements
|   |-- user-stories.md        User stories with acceptance criteria
|   `-- sprint-log.md          Sprint goal, standups, review and retrospective
`-- src/
    `-- README.md              Source code placeholder
```

## Roadmap

- [x] Week 2: Draft the problem statement, requirements and user stories
- [ ] Week 3: Complete Sprint 1 — acceptance criteria, numbered requirements, project structure and roadmap
- [ ] Week 3: Complete three merged pull requests, close the issues and move the board cards to Done
- [ ] Week 3: Complete the partner review and sprint retrospective
- [x] Review and verify evidence supporting the problem statement
- [x] Choose the specialised technology (machine learning) and list credible sources
- [x] Outline the technology explanation
- [ ] Week 4: Submit Assignment 1
- [ ] By Week 19: Compare candidate models (random forest, XGBoost) and identify the best one
- [ ] By Week 23: Develop the mobile app and dashboard that use the chosen model
- [ ] By Week 26: Evaluate the app through user testing with a questionnaire

## Author

Nurin Irdina Safiah binti Arif Sarjana (for Final Year Project). Supervisor: Ts. Dr. Razulaimi bin Razali.

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
