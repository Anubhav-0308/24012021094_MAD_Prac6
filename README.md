https://github.com/user-attachments/assets/6d50bf78-8e41-4dcc-a0a2-b049d4e9680e

# ⏰ Alarm App

An Android Alarm application developed using **Kotlin** and **Android Studio** as a practical/academic project for **U.V. Patel College of Engineering, Ganpat University**.

The app allows users to set an alarm using a time picker and cancel the scheduled alarm. It also includes a splash screen, animated UI elements, and Android `AlarmManager`, `BroadcastReceiver`, and `Service` components.

---

## 📱 Project Overview

**Project Name:** Alarm App 
**Platform:** Android  
**IDE:** Android Studio  
**Language:** Kotlin  
**UI:** XML + Material Components  
**Application Type:** Android Application

### Main Features

- 🎬 Animated splash screen
- ⏰ Create an alarm for a selected time
- ❌ Cancel an active alarm
- 🔔 Alarm scheduling using `AlarmManager`
- 📡 Alarm trigger using `BroadcastReceiver`
- ⚙️ Background alarm handling using `AlarmService`
- 🔐 Exact alarm permission handling
- ❤️ Animated UI elements
- 🎨 Material CardView based interface

---

## 🖼️ Application Screenshots

### Splash Screen

The application starts with a splash screen displaying the Ganpat University / U.V. Patel College of Engineering branding.

### Main Alarm Screen

The main screen contains:

- Alarm animation
- "Create Alarm Time" section
- Create Alarm button
- Cancel Alarm button
- Selected alarm time display

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Kotlin | Application development |
| Android Studio | Development environment |
| XML | UI design |
| MaterialCardView | Modern card-based UI |
| AlarmManager | Schedule alarms |
| BroadcastReceiver | Receive alarm broadcasts |
| Service | Handle alarm operation |
| AnimationDrawable | Frame animations |
| TimePickerDialog | Select alarm time |

---

## 📂 Project Structure

```text
app/
└── src/
    └── main/
        ├── java/
        │   └── com.example.a24012021094_anubhav_prac6/
        │       ├── MainActivity.kt
        │       ├── SplashActivity.kt
        │       ├── AlarmBroadcastReceiver.kt
        │       └── AlarmService.kt
        │
        ├── res/
        │   ├── anim/
        │   │   └── twin_animation.xml
        │   │
        │   ├── drawable/
        │   │   ├── alarm_animation_list.xml
        │   │   ├── heart_animation_list.xml
        │   │   ├── uvpce_animation_list.xml
        │   │   ├── rectangle.xml
        │   │   └── alarm images
        │   │
        │   └── layout/
        │       ├── activity_main.xml
        │       └── activity_splash.xml
        │
        └── AndroidManifest.xml
```

---

## 🔄 How the Application Works

The basic working flow is:

```text
Application Start
       ↓
SplashActivity
       ↓
Splash Animation
       ↓
MainActivity
       ↓
Select Alarm Time
       ↓
AlarmManager
       ↓
PendingIntent
       ↓
AlarmBroadcastReceiver
       ↓
AlarmService
       ↓
Alarm Action
```

---

## ⏰ Alarm Scheduling

When the user selects a time:

1. `TimePickerDialog` opens.
2. User selects the required hour and minute.
3. `MainActivity` creates a `Calendar` time.
4. `AlarmManager` schedules the alarm.
5. A `PendingIntent` is created for `AlarmBroadcastReceiver`.
6. When the scheduled time arrives, the receiver is triggered.
7. `AlarmService` handles the alarm operation.

The application uses:

```kotlin
AlarmManager.RTC_WAKEUP
```

to schedule the alarm.

---

## 📡 BroadcastReceiver

`AlarmBroadcastReceiver` receives the alarm broadcast.

The receiver uses three constants:

```kotlin
const val SERVICE_KEY = "Service1"
const val START_VAL = "start"
const val STOP_VAL = "stop"
```

When the received value is `"start"`, the service is started.

When the value is `"stop"`, the service is stopped.

---

## ⚙️ AlarmService

`AlarmService` is an Android `Service` responsible for handling the alarm operation after the `BroadcastReceiver` receives the scheduled broadcast.

The service can be extended to:

- Play an alarm sound
- Show a notification
- Vibrate the device
- Display an alarm screen
- Perform other background alarm actions

---

## 🔐 Exact Alarm Permission

The application uses:

```xml
<uses-permission
    android:name="android.permission.SCHEDULE_EXACT_ALARM" />
```

The app checks whether exact alarm scheduling is allowed:

```kotlin
alarmManager.canScheduleExactAlarms()
```

If permission is not available, the application opens the system settings so the user can grant exact alarm permission.

---



## 🚀 How to Run the Project

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
```

### Step 2: Open in Android Studio

Open the project using:

```text
Android Studio → Open → Select Project Folder
```

### Step 3: Sync Gradle

Allow Android Studio to download and configure the required dependencies.

### Step 4: Connect an Android Device

Enable:

```text
Developer Options
USB Debugging
```

on the Android device.

### Step 5: Run

Click the **Run ▶** button in Android Studio.

---

## 📋 Permissions

The application requires the following permission:

```xml
android.permission.SCHEDULE_EXACT_ALARM
```

This permission is required for scheduling exact alarms on supported Android versions.

---

## 🎯 Academic Purpose

This project demonstrates important Android development concepts including:

- Activity lifecycle
- Intent
- BroadcastReceiver
- Service
- AlarmManager
- PendingIntent
- TimePickerDialog
- Runtime/system permission handling
- XML layouts
- Material UI components
- Android animations
