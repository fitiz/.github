# Fitiz

Welcome to Fitiz, a comprehensive fitness application designed to motivate, track, and engage users in health and fitness activities through location-based challenges and community engagement.
## Techstack

<img src="https://skillicons.dev/icons?i=java,react,kubernetes,docker,redis,spring,gcp,postgres,gradle,kafka,github,githubactions" />

## Features

-   **Location-Based Challenges:** Participate in fitness challenges specific to your location, encouraging outdoor activities and exploration.
-   **Real-Time Leaderboards:** Track your progress and compete with others in real-time with our dynamic leaderboard system.
-   **Fitness Metrics Tracking:** Monitor various fitness metrics to analyze and improve your performance over time.

## UI
[![rn](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://github.com/fitiz/fitiz-react-native)

-   **Cross-Platform Support:** Access Fitiz on your preferred device with our React Native frontend, ensuring a seamless user experience.
-   **[fitiz-react-native](https://github.com/fitiz/fitiz-react-native):** Infinite Red's battle-tested React Native project boilerplate + Expo

<img width="150" alt="Screenshot 2024-02-12 at 6 22 24 PM" src="https://github.com/fitiz/.github/assets/23321849/ff943b7b-33f8-4355-85e0-fca00fc611e5">
<img width="140" alt="Screenshot 2024-02-09 at 5 31 42 PM" src="https://github.com/fitiz/.github/assets/23321849/94595623-c10f-489d-9569-ae367fecde6d">

## Services

Fitiz is built using microservices architecture to ensure scalability, flexibility, and robustness. The system is composed of the following services:

-   **[Challenge Service](https://github.com/fitiz/challenge-service):** Handles creation, management, and participation in fitness challenges.
-   **[Fitness Metrics Service](https://github.com/fitiz/fitness-metrics-service):** Collects and processes fitness-related metrics and data.
-   **[User Service](https://github.com/fitiz/user-service):** Manages user accounts, authentication, and profile information.
-   **[Location Service](https://github.com/fitiz/location-service):** (not implemented yet) Manages location data and integration with external mapping services.
-   **[Explore Service](https://github.com/fitiz/explore-service):** (not implemented yet) Facilitates discovery of new locations and challenges.
-   **[api-gateway](https://github.com/fitiz/api-gateway)**

-   **[discovery-service](https://github.com/fitiz/discovery-service)**

**Consumer groups for Kafka:**
-   **[cs-redis-consumer](https://github.com/fitiz/cs-redis-consumer):** Updates sorted set in Redis + Publishes leaderboard-change topic.
-   **[cs-pg-consumer](https://github.com/fitiz/cs-pg-consumer):** Writes data to database to make it persistent. (we need to get persistent data for the sync mechanism in case of any failure in-memory database)
-   **[cs-leaderboard-change-consumer](https://github.com/fitiz/cs-leaderboard-change-consumer):** Manages real-time updates and top-10 leaderboard cache in Redis.
-   **[leaderboard-websocket-service](https://github.com/fitiz/leaderboard-websocket-service):** Pushed leaderboard cache to challenge specific WebSocket channel.

## Architecture Overview

<img width="600" alt="Screenshot 2024-02-12 at 6 22 24 PM" src="https://github.com/fitiz/.github/assets/23321849/42c66047-35d3-4c40-847d-0f9ca3fbb9a0">

<img width="600" alt="Screenshot 2024-02-12 at 6 22 24 PM" src="https://github.com/fitiz/.github/assets/23321849/94a97d27-8edc-4768-9bfc-f473cc460957">

## CI/CD Workflow

- Workflow file: [workflow.yml](https://github.com/fitiz/challenge-service/blob/main/.github/workflows/build.yml)

![fitiz-app - Page 1 Frame 3](https://github.com/fitiz/.github/assets/23321849/5d6c2388-58e2-4486-8da0-0050dc0801a9)

#### K8s configs + Kustomize overlays:

- https://github.com/fitiz/challenge-service/tree/main/deployment

## Demo
- https://drive.google.com/file/d/1hA9vJqauV0E-8ZfcsvV8KIXgSuMjcI1O/view?usp=sharing

## Sources
- https://github.com/fitiz
- https://www.strava.com/challenges
- https://apps.apple.com/us/app/walker-pedometer-the-game/id1455639400
- https://github.com/GoogleCloudPlatform/cloud-sql-proxy
- https://www.youtube.com/watch?v=5XfgT9A9PHw
- https://blog.jannikwempe.com/github-actions-trunk-based-development
- https://dev.to/n3wt0n/everything-you-need-to-know-about-github-actions-environments-9p7
- https://github.com/fitiz/challenge-service/blob/main/.github/workflows/build.yml
- https://github.com/fitiz/challenge-service/tree/main/deployment
- https://devopscube.com/kustomize-tutorial/
- https://systemdesign.one/leaderboard-system-design/
- https://medium.com/@ilakk2023/designing-a-real-time-leaderboard-system-using-kafka-df6d44cdbd49
- https://redis.com/solutions/use-cases/leaderboards/
- https://redis.io/docs/data-types/sorted-sets/
- https://medium.com/@mayilb77/design-a-real-time-leaderboard-system-for-millions-of-users-08b96b4b64ce
- https://migratorydata.com/blog/realtime-gamification-to-millions-of-users/
- https://www.youtube.com/watch?v=MUKlxdBQZ7g
- https://github.com/aleksandarskrbic/kafka-leaderboard
- https://storyset.com/
- https://docs.expo.dev/eas-update/github-actions/

## Contributing

We welcome contributions from the community! Whether you're interested in fixing bugs, adding new features, or improving documentation, your help is appreciated. Please see our contributing guidelines for more information.
