# 🚗 Car Monitoring App – Feasibility & Implementation Plan

A mobile application built using **Flutter** and **Supabase** to help company drivers log trips, fuel usage, and associated metadata. This project aims to deliver a working **proof-of-concept (PoC)** within a 12-hour development sprint, emphasizing clean data flow, minimal UI, and fast iteration using AI-assisted development.

---

## 📌 1. Introduction

- **Objective**: Build a mobile app that allows drivers to log daily trips, refueling details, and related metadata.
- **Frontend**: Flutter (cross-platform development)
- **Backend**: Supabase (authentication, PostgreSQL DB, real-time sync)

⚡ Target: **Functional MVP within 12 hours** using AI for boilerplate and repetitive logic.

---

## 🧩 2. Scope & Core Features

### ✅ Trip Logging
- Start/end timestamps  
- Odometer readings (for distance calculation)  
- Trip purpose & optional stops  

### ⛽ Refueling Management
- Time & date of refuel  
- Liters and cost input  
- Auto-calculated fuel efficiency (km/L)  

### 👥 Driver & Passenger Data
- Authenticated driver profiles  
- Tag passengers (employees, engineers, etc.)  

### 📊 Administrative Interface
- List and filter trips  
- View metrics (average distance, fuel efficiency)  

> 🎯 *Note*: Focus will be on functionally correct implementations, not complete UI polish.

---

## 🛠️ 3. Technology Stack

### Flutter
- Cross-platform mobile development
- Rapid UI building
- Large plugin ecosystem

### Supabase
- PostgreSQL with real-time features
- Built-in authentication
- Schema-driven development
- Row-level security (RLS)

### Platform-Specific Configurations

#### iOS & macOS
1. **Network Permissions**
   - Add to `ios/Runner/Info.plist`:
     ```xml
     <key>NSAppTransportSecurity</key>
     <dict>
       <key>NSAllowsArbitraryLoads</key>
       <true/>
     </dict>
     ```
   - Add to `macos/Runner/DebugProfile.entitlements` and `macos/Runner/Release.entitlements`:
     ```xml
     <key>com.apple.security.network.client</key>
     <true/>
     ```

2. **iOS Entitlements**
   - Add to `ios/Runner/Runner.entitlements`:
     ```xml
     <key>com.apple.security.network.client</key>
     <true/>
     ```

> ⚠️ **Note**: These configurations are necessary for allowing network connections to Supabase. Without them, you may encounter connection issues on iOS and macOS platforms.

---

## 🧪 4. Proposed Implementation Phases

### 📁 Phase 1: Schema & Data Models (2–3 hrs)
- Set up Supabase tables:
  - `drivers`, `trips`, `refueling_logs`
- Create Dart data models

### 🔐 Phase 2: Auth & Basic UI (3–4 hrs)
- Implement Supabase Auth
- Build login/signup screens
- Create simple trip dashboard

### 🧾 Phase 3: Core App Logic (4–5 hrs)
- Trip entry form with start/end odometers
- Refueling entry and fuel efficiency logic
- Admin view with filtering and summaries

### 🧹 Phase 4: Testing & Enhancements (remainder)
- Input validations
- Data integrity checks
- UI/UX tweaks

---

## ⚠️ 5. Potential Bottlenecks

- **Data accuracy issues** (e.g., skipped odometer inputs)
- **Row-level security configuration**
- **UX trade-offs** under time pressure
- **Offline access or real-time sync**, if required, could exceed scope

---

## 🧭 6. Strategy for 12-Hour Completion

- Define strict MVP goals  
- Use AI tools for model generation and UI scaffolding  
- Maintain modular code separation  
- Prioritize functionality over polish  
- Test each module before proceeding to the next

---

## ✅ 7. Conclusion

This app is feasible to build as a basic PoC within 12 hours. With clear goals, efficient tool use, and tight scope management, you can achieve an MVP that includes trip tracking, fuel management, user authentication, and an admin view—laying the foundation for future enhancements.