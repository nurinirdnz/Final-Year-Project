# User Stories

Format: As a [type of user], I want [goal], so that [reason or benefit].

1. As an environment officer, I want to see all current hotspots on a map, so that I know where fires are burning near Sarawak. (FR6)
   - Acceptance criteria:
     - Every hotspot in the study area from the latest satellite release appears on the map at its real location.
     - Clicking a hotspot shows its location, detection time and fire strength.

2. As an environment officer, I want each hotspot labelled as a persistent fire or a short-lived detection, so that I can ignore brief detections. (FR3)
   - Acceptance criteria:
     - Every hotspot shows one class: persistent fire or short-lived detection.
     - The two classes are shown in different colours, with a legend that explains them.

3. As a disaster management officer, I want a next-day haze forecast for each monitoring station, so that I can warn the public early. (FR4)
   - Acceptance criteria:
     - Each selected Sarawak station shows whether the API is expected to exceed 100 the next day.
     - The forecast shows the date it applies to.

4. As a fire and rescue officer, I want hotspots ranked from most to least dangerous, so that I know which fires to check first. (FR5)
   - Acceptance criteria:
     - Hotspots are listed from the highest to the lowest risk score.
     - Each hotspot in the list shows its class, fire strength, distance to Sarawak and wind direction.

5. As a dashboard user, I want the dashboard to update by itself, so that I always see the latest situation. (FR1)
   - Acceptance criteria:
     - New satellite data appears on the dashboard within 5 minutes of its release, with no manual refresh.
     - The last-updated time changes after every update.

6. As a dashboard user, I want to see when the satellite captured the data, so that I know how old the information is. (FR7)
   - Acceptance criteria:
     - The dashboard shows the date and time the satellite captured the data.
     - The capture time is shown separately from the last-updated time.
