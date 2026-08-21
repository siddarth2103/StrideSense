<div align="center">
  <img src="assets/banner.svg" alt="StrideSense — AI-powered fitness tracking" width="100%" />

  <br />

  [![Google Play](https://img.shields.io/badge/Google_Play-Download-34A853?style=for-the-badge&logo=googleplay&logoColor=white)](https://play.google.com/store/apps/details?id=com.siddarth.stridesense)
  ![Flutter](https://img.shields.io/badge/Flutter-Dart-02569B?style=for-the-badge&logo=flutter&logoColor=white)
  ![Firebase](https://img.shields.io/badge/Firebase-Cloud_Sync-FFCA28?style=for-the-badge&logo=firebase&logoColor=111)
  ![Spring Boot](https://img.shields.io/badge/Spring_Boot-Backend-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)

  **A production Android fitness companion combining hardware step sensing, GPS walk tracking, cloud synchronization, and AI-powered coaching.**
</div>

## About StrideSense

StrideSense is a full-stack fitness application built and launched on Google Play. It turns Android sensor data into a dependable daily activity experience while keeping manual GPS walks, cloud-backed profiles, and AI coaching within one focused product.

The project was designed around real mobile constraints: locked screens, process recreation, device reboots, midnight rollover, delayed sensor callbacks, intermittent connectivity, and multiple account scopes.

## Product highlights

- **Automatic step tracking** using Android's hardware step counter, including locked-screen operation
- **Live Walk** sessions with GPS distance, current and average speed, duration, and accuracy status
- **AI Health Coach** with activity-aware, non-medical fitness guidance
- **Goals and motivation** through streaks, statistics, reminders, and leaderboards
- **Offline-first storage** with local persistence and secure cloud synchronization
- **Account isolation** for guest and Google/Firebase profiles
- **Local-time behavior** for daily rollover, reminders, and AI usage limits
- **Accessible interface** with light and dark themes

## Product visuals

<p align="center">
  <img src="assets/home-stats-dark.jpeg" alt="StrideSense home statistics in dark mode" width="240" />
  &nbsp;
  <img src="assets/trends-dark.jpeg" alt="StrideSense weekly activity trends" width="240" />
  &nbsp;
  <img src="assets/health-metrics.jpeg" alt="StrideSense health metrics" width="240" />
</p>

<p align="center">
  <img src="assets/home-stats-light.jpeg" alt="StrideSense home statistics in light mode" width="240" />
  &nbsp;
  <img src="assets/preferences.jpeg" alt="StrideSense preferences and AI coaching settings" width="240" />
</p>

<table>
  <tr>
    <td align="center" width="50%">
      <img src="assets/app-icon.png" alt="StrideSense app icon" width="230" />
      <br /><strong>Published Android application</strong>
    </td>
    <td align="center" width="50%">
      <img src="assets/ai-assistant.png" alt="StrideSense AI assistant" width="230" />
      <br /><strong>StrideSense AI Health Coach</strong>
    </td>
  </tr>
</table>

<p align="center">
  <img src="assets/fitness-coach.png" alt="StrideSense fitness coach artwork" width="780" />
</p>

## System architecture

<p align="center">
  <img src="assets/architecture.svg" alt="StrideSense system architecture" width="900" />
</p>

### Technology stack

| Layer | Technologies |
|---|---|
| Mobile | Flutter, Dart, Android platform APIs |
| Activity tracking | `TYPE_STEP_COUNTER`, foreground services, background processing |
| Walk tracking | Foreground location service, GPS stream processing, Google Maps |
| Local data | Hive, SharedPreferences |
| Identity and cloud | Firebase Authentication, Cloud Firestore |
| Backend | Java, Spring Boot, Google Cloud Run |
| Intelligence | Gemini API |
| Engagement | Local notifications, goals, streaks, leaderboards |
| Monetization | Google AdMob |

## Engineering challenges

Building a step counter that works in production required more than reading a sensor value. StrideSense handles:

- Step continuity across app termination, service restart, reboot, and midnight
- Cross-isolate synchronization and protection from delayed or out-of-order events
- Monotonic daily totals without artificial step compensation
- Foreground-service recovery while keeping a single sensor owner
- GPS noise and stationary-drift filtering without suppressing genuine slow walking
- Cold-start initialization without exposing data from the wrong account
- Per-account local and cloud state during sign-in, sign-out, and account switching
- Android notification, foreground-service, privacy, and release requirements

## Privacy-conscious design

- Location access begins only after the user manually starts a Live Walk
- An ongoing Android notification is shown during active GPS tracking
- Exact coordinates and route points are not persisted or uploaded
- Saved walk records contain summary metrics only
- Health and profile data remain isolated by account scope
- Users can request account and cloud-data deletion

## Availability

StrideSense is available on Google Play:

**https://play.google.com/store/apps/details?id=com.siddarth.stridesense**

## Repository notice

This is a **public product showcase repository** created for portfolio, résumé, and professional-review purposes. It intentionally contains no application source code, backend source code, credentials, service-account files, signing material, or production configuration.

The StrideSense implementation is proprietary and remains private.

---

<div align="center">
  Built and shipped by <a href="https://github.com/siddarth2103">Siddarth</a>.
</div>
