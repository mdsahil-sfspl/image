# KiloMeters - Wireframe Specification Document

**Prepared by:** Sampurna IT Team  
**Version:** 1.0  
**Date:** November 11, 2025  
**Status:** 🟡 In Review

---

## Document Version Control

| Version | Date | Author | Change Description |
|---------|------|--------|-------------------|
| 0.1 | 2025-10-20 | Anupam Das | Initial wireframe draft for core modules |
| 0.2 | 2025-10-25 | Design Team | Added responsive layouts and interaction states |
| 1.0 | 2025-11-11 | Anupam Das | Complete wireframe specification with all modules |

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Design System Overview](#2-design-system-overview)
3. [User Flow Diagrams](#3-user-flow-diagrams)
4. [Wireframe Specifications](#4-wireframe-specifications)
5. [Component Library](#5-component-library)
6. [Responsive Behaviors](#6-responsive-behaviors)
7. [Interaction Patterns](#7-interaction-patterns)
8. [Appendices](#8-appendices)

---

## 1. Introduction

### 1.1 Purpose
This document provides detailed wireframe specifications for the **KiloMeters** web application, a field activity tracking and fuel reimbursement management system for Sampurna Financial Services.

### 1.2 Scope
Covers all user-facing screens across:
- **Employee Module**: Dashboard, Bike Reading, Task Management
- **Manager Module**: Team oversight, Approvals
- **Admin Module**: Configuration, User Management, Reports
- **Accounts Module**: Reimbursement processing

### 1.3 Audience
- UI/UX Designers
- Frontend Developers (ReactJS)
- Backend Developers (Node.js)
- Product Managers
- QA Team

### 1.4 Wireframe Conventions

**Visual Elements:**
```
┌─────────────┐
│   [Button]  │  = Interactive button
└─────────────┘

┌─────────────┐
│ Input Field │  = Text input field
└─────────────┘

┌─────────────┐
│ ☰ Menu      │  = Navigation menu
└─────────────┘

[Icon] Label    = Icon with text label

━━━━━━━━━━━━━  = Section divider
```

**Status Indicators:**
- 🔵 Draft
- 🟡 In Review  
- 🟢 Approved
- 🔴 Revision Needed

---

## 2. Design System Overview

### 2.1 Color Palette

```
Primary Colors:
- Primary Blue: #2196F3 (Buttons, Links, Active states)
- Primary Dark: #1976D2 (Hover states, Headers)
- Primary Light: #BBDEFB (Backgrounds, Highlights)

Semantic Colors:
- Success Green: #4CAF50 (Approved, Success messages)
- Warning Orange: #FF9800 (Pending, Warnings)
- Error Red: #F44336 (Errors, Rejections, Delete)
- Info Blue: #2196F3 (Information, Neutral actions)

Neutral Colors:
- Text Primary: #212121 (Headings, Primary text)
- Text Secondary: #757575 (Secondary text, Labels)
- Border: #E0E0E0 (Dividers, Card borders)
- Background: #FAFAFA (Page background)
- White: #FFFFFF (Card backgrounds, Content areas)
```

### 2.2 Typography Scale

```
H1: Roboto Bold, 32px, Line Height 40px
H2: Roboto Bold, 24px, Line Height 32px
H3: Roboto Medium, 20px, Line Height 28px
H4: Roboto Medium, 18px, Line Height 24px
Body Large: Roboto Regular, 16px, Line Height 24px
Body: Roboto Regular, 14px, Line Height 20px
Body Small: Roboto Regular, 12px, Line Height 18px
Button: Roboto Medium, 14px, Uppercase
Caption: Roboto Regular, 12px, Line Height 16px
```

### 2.3 Spacing System

```
Base Unit: 8px

Spacing Scale:
xs: 4px
sm: 8px
md: 16px
lg: 24px
xl: 32px
2xl: 48px
3xl: 64px
```

### 2.4 Grid System

- **Desktop**: 12-column grid, 1440px max-width, 24px gutters
- **Tablet**: 8-column grid, 768px - 1024px, 16px gutters
- **Mobile**: 4-column grid, 320px - 767px, 16px gutters

---

## 3. User Flow Diagrams

### 3.1 Employee Daily Reading Flow

```
[Login] 
   ↓
[Dashboard]
   ↓
[Click "Submit Reading"] ───→ [Check Geofence]
   ↓                              ↓ (Outside)
[Select IN/OUT]              [Error: Outside Branch Radius]
   ↓
[Enter Odometer]
   ↓
[Capture Photo]
   ↓
[Review & Submit] ───→ [Validation]
   ↓                      ↓ (Fail)
[Success]            [Show Errors]
   ↓
[Dashboard Updated]
```

### 3.2 Manager Approval Flow

```
[Manager Dashboard]
   ↓
[Pending Approvals (Badge)]
   ↓
[View Pending List]
   ↓
[Select Reading]
   ↓
[View Details: Photos, GPS, Distance]
   ↓
[Approve / Reject Decision]
   ↓ (Reject)          ↓ (Approve)
[Add Comment]      [Confirm Approval]
   ↓                   ↓
[Send to Employee] [Update to Accounts]
```

### 3.3 Task Assignment Flow

```
[Manager: Task Module]
   ↓
[Create New Task]
   ↓
[Select Template / Custom]
   ↓
[Assign to Employee(s)]
   ↓
[Set Duration & Details]
   ↓
[Submit Task]
   ↓
[Employee Receives Notification]
   ↓
[Employee: View Task]
   ↓
[Start Task → Route Tracking Begins]
   ↓
[Complete Task → Upload Completion Photo]
   ↓
[Manager: Review & Approve]
```

---

## 4. Wireframe Specifications

## 4.1 Login Screen

**Screen ID**: AUTH-LOGIN-001  
**Route**: /login  
**User Role**: All (Unauthenticated)  
**Status**: 🟢 Approved

### Layout Wireframe

```
┌─────────────────────────────────────────────────────────────┐
│                                                               │
│                        [LOGO: KiloMeters]                    │
│                    Field Activity Tracker                    │
│                                                               │
│                  ┌────────────────────────┐                  │
│                  │                        │                  │
│                  │  [H2] Welcome Back     │                  │
│                  │                        │                  │
│                  │  ┌──────────────────┐ │                  │
│                  │  │ 📧 Email         │ │                  │
│                  │  │ [Input Field]    │ │                  │
│                  │  └──────────────────┘ │                  │
│                  │                        │                  │
│                  │  ┌──────────────────┐ │                  │
│                  │  │ 🔒 Password      │ │                  │
│                  │  │ [Input Field]    │ │                  │
│                  │  │            [👁]   │ │                  │
│                  │  └──────────────────┘ │                  │
│                  │                        │                  │
│                  │  ☐ Remember Me        │                  │
│                  │                        │                  │
│                  │  ┌──────────────────┐ │                  │
│                  │  │   SIGN IN        │ │                  │
│                  │  └──────────────────┘ │                  │
│                  │                        │                  │
│                  │  [Forgot Password?]   │                  │
│                  │                        │                  │
│                  └────────────────────────┘                  │
│                                                               │
│              © 2025 Sampurna Financial Services              │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

### Component Specifications

| Component ID | Type | Behavior | Validation |
|--------------|------|----------|------------|
| IMG-LOGO-001 | Image | Static display | N/A |
| INPUT-EMAIL-001 | Email Input | Auto-lowercase, Trim spaces | Email format check |
| INPUT-PASS-001 | Password Input | Masked by default | Min 8 characters |
| CHK-REMEMBER-001 | Checkbox | Optional | N/A |
| BTN-SIGNIN-001 | Primary Button | Disabled until valid form | Submit on Enter key |
| LINK-FORGOT-001 | Text Link | Navigate to /reset-password | N/A |

### Interaction States

**Button States:**
```
[BTN-SIGNIN-001]
- Default: Blue background, white text
- Hover: Darker blue, cursor pointer
- Loading: Show spinner icon, text "Signing in...", disabled
- Disabled: Gray background, gray text
- Error: Red border on form, error message above button
```

**Form Validation:**
- **Real-time**: Email format checked on blur
- **On Submit**: Both fields required, proper credentials
- **Error Display**: Red text below field, red border on input
- **Success**: Redirect to /dashboard after JWT storage

### API Integration

```javascript
// POST /api/auth/login
Request Body:
{
  "email": "user@example.com",
  "password": "********"
}

Success Response (200):
{
  "success": true,
  "token": "jwt_token_here",
  "user": {
    "id": 123,
    "name": "John Doe",
    "role": "employee",
    "branch_id": 5
  }
}

Error Response (401):
{
  "success": false,
  "message": "Invalid email or password"
}
```

### Responsive Behavior

**Desktop (> 1024px):**
- Login card: 450px width, centered
- Logo: 240px width
- Generous whitespace

**Tablet (768px - 1024px):**
- Login card: 70% width, centered
- Logo: 200px width

**Mobile (< 768px):**
- Login card: 90% width
- Logo: 180px width
- Form inputs: Full width minus 16px padding
- Stack all elements vertically

---

## 4.2 Employee Dashboard

**Screen ID**: DASH-EMP-001  
**Route**: /dashboard  
**User Role**: Employee, Manager  
**Status**: 🟢 Approved

### Layout Wireframe

```
┌─────────────────────────────────────────────────────────────────────────┐
│ ☰ KiloMeters        [Dashboard] [Readings] [Tasks]    🔔(2)  👤 John   │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                           │
│  [H1] Dashboard                                      📅 Nov 11, 2025    │
│                                                                           │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │
│  │ 📊 This     │  │ 🎯 Pending  │  │ ✅ Completed│  │ 💰 Est.     │  │
│  │ Month       │  │ Approvals   │  │ Tasks       │  │ Reimburse   │  │
│  │             │  │             │  │             │  │             │  │
│  │ 1,234 KM    │  │     3       │  │     12      │  │  ₹ 8,345   │  │
│  │ ↗ +15%      │  │             │  │             │  │             │  │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │
│                                                                           │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
│                                                                           │
│  [H2] Quick Actions                                                      │
│                                                                           │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐  │
│  │ 📸 Submit Reading │  │ ➕ Request Task   │  │ 🗺️ View Routes   │  │
│  └───────────────────┘  └───────────────────┘  └───────────────────┘  │
│                                                                           │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
│                                                                           │
│  [H2] Recent Activity                                 [View All →]      │
│                                                                           │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ 📅 Nov 10, 2025  │  IN: 12,345 KM  │  OUT: 12,456 KM  │  ✅ Appr..│  │
│  │ Branch: Kolkata-1  │  Distance: 111 KM  │  Amount: ₹ 750        │  │
│  ├──────────────────────────────────────────────────────────────────┤  │
│  │ 📅 Nov 09, 2025  │  IN: 12,200 KM  │  OUT: 12,345 KM  │  ⏳ Pend..│  │
│  │ Branch: Kolkata-1  │  Distance: 145 KM  │  Amount: ₹ 980        │  │
│  ├──────────────────────────────────────────────────────────────────┤  │
│  │ 📅 Nov 08, 2025  │  IN: 12,050 KM  │  OUT: 12,200 KM  │  ✅ Appr..│  │
│  │ Branch: Kolkata-1  │  Distance: 150 KM  │  Amount: ₹ 1,013      │  │
│  └──────────────────────────────────────────────────────────────────┘  │
│                                                                           │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
│                                                                           │
│  [H2] Distance Trend (Last 7 Days)                                      │
│                                                                           │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │                                                                    │  │
│  │  200 ┤                                          •                 │  │
│  │      │                                      •       •             │  │
│  │  150 ┤                  •           •   •               •         │  │
│  │      │          •   •       •                               •     │  │
│  │  100 ┤      •                                                     │  │
│  │      │  •                                                         │  │
│  │   50 ┤                                                            │  │
│  │      └────────────────────────────────────────────────────────   │  │
│  │       Nov5 Nov6 Nov7 Nov8 Nov9 Nov10 Nov11                      │  │
│  │                                                                    │  │
│  └──────────────────────────────────────────────────────────────────┘  │
│                                                                           │
└─────────────────────────────────────────────────────────────────────────┘
```

### Component Specifications

#### Navigation Bar [NAV-001]
| Element | ID | Behavior |
|---------|-----|----------|
| Hamburger Menu | BTN-MENU-001 | Toggle side drawer (mobile) |
| Logo + Title | LINK-HOME-001 | Navigate to /dashboard |
| Nav Links | LINK-NAV-* | Active state on current page |
| Notification Bell | BTN-NOTIF-001 | Show badge count, open dropdown |
| User Avatar | BTN-PROFILE-001 | Open dropdown: Profile, Settings, Logout |

#### Stats Cards [CARD-STATS-*]
```
[CARD-STATS-001: This Month KM]
- Data Source: GET /api/dashboard/stats?period=month
- Update: Real-time on new approval
- Trend Indicator: Green ↗ (increase), Red ↘ (decrease)
- Click Action: Navigate to /readings?filter=month

[CARD-STATS-002: Pending Approvals]
- Data Source: GET /api/readings/pending-count
- Badge Color: Orange (pending)
- Click Action: Navigate to /readings?status=pending

[CARD-STATS-003: Completed Tasks]
- Data Source: GET /api/tasks/completed-count
- Badge Color: Green
- Click Action: Navigate to /tasks?status=completed

[CARD-STATS-004: Estimated Reimbursement]
- Data Source: Calculated from pending + approved readings
- Format: Indian Rupee (₹)
- Click Action: Navigate to /accounts/my-reimbursements
```

#### Quick Action Buttons [BTN-ACTION-*]
```
[BTN-ACTION-001: Submit Reading]
- Primary Action
- Opens: Reading submission modal
- Pre-check: Geolocation permission

[BTN-ACTION-002: Request Task]
- Secondary Action
- Opens: Task request form
- Manager notification sent

[BTN-ACTION-003: View Routes]
- Secondary Action
- Navigate to: /routes
- Shows GPS tracked routes
```

#### Recent Activity Table [TABLE-ACTIVITY-001]
- **Columns**: Date, IN Reading, OUT Reading, Status
- **Row Click**: Navigate to /readings/{id}
- **Status Badges**: 
  - ✅ Approved (Green)
  - ⏳ Pending (Orange)
  - ❌ Rejected (Red)
- **Pagination**: Show 5 rows, "View All" link
- **Empty State**: "No recent activity. Submit your first reading!"

#### Distance Trend Chart [CHART-DIST-001]
- **Type**: Line chart (Recharts library)
- **Data Points**: Last 7 days
- **Y-Axis**: Distance in KM
- **X-Axis**: Dates
- **Interaction**: Hover tooltip shows exact values
- **Data Source**: GET /api/dashboard/trend?days=7

### API Endpoints

```javascript
// GET /api/dashboard/stats
Response:
{
  "month_km": 1234,
  "month_change_percent": 15,
  "pending_approvals": 3,
  "completed_tasks": 12,
  "estimated_reimbursement": 8345
}

// GET /api/dashboard/recent-activity
Response:
{
  "activities": [
    {
      "id": 123,
      "date": "2025-11-10",
      "in_reading": 12345,
      "out_reading": 12456,
      "distance": 111,
      "amount": 750,
      "status": "approved",
      "branch_name": "Kolkata-1"
    }
  ]
}

// GET /api/dashboard/trend?days=7
Response:
{
  "trend": [
    {"date": "2025-11-05", "km": 145},
    {"date": "2025-11-06", "km": 132},
    ...
  ]
}
```

### Responsive Behavior

**Desktop (> 1024px):**
- 4-column grid for stats cards
- Full navigation bar visible
- Chart: 800px width
- Table: Full data visible

**Tablet (768px - 1024px):**
- 2-column grid for stats cards
- Collapsible navigation
- Chart: Responsive width
- Table: Scroll horizontally if needed

**Mobile (< 768px):**
- 1-column stack for stats cards
- Hamburger menu navigation
- Chart: Simplified, touch-scrollable
- Table: Convert to card list view
- Quick action buttons: Full width, stacked

### Accessibility

- **Keyboard Navigation**: All interactive elements tabbable
- **Screen Reader**: ARIA labels on all icons and stats
- **Focus Indicators**: 2px blue outline on focus
- **Color Contrast**: All text meets WCAG AA (4.5:1)
- **Alt Text**: Chart has descriptive aria-label

---

## 4.3 Bike Reading Submission

**Screen ID**: READ-SUBMIT-001  
**Route**: /readings/submit (Modal)  
**User Role**: Employee  
**Status**: 🟢 Approved

### Layout Wireframe (Modal)

```
                    ┌──────────────────────────────────┐
                    │ [X] Submit Bike Reading          │
                    ├──────────────────────────────────┤
                    │                                  │
                    │  [Step 1/4] Select Type          │
                    │                                  │
                    │  ┌────────────┐  ┌────────────┐ │
                    │  │    IN      │  │    OUT     │ │
                    │  │ 🟢 Active  │  │  ○ Select  │ │
                    │  └────────────┘  └────────────┘ │
                    │                                  │
                    │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
                    │                                  │
                    │  [Step 2/4] Enter Reading        │
                    │                                  │
                    │  Odometer Reading (KM)           │
                    │  ┌────────────────────────────┐ │
                    │  │  12,456                    │ │
                    │  └────────────────────────────┘ │
                    │                                  │
                    │  Last Reading: 12,345 KM (IN)   │
                    │  Distance: 111 KM ✓             │
                    │                                  │
                    │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
                    │                                  │
                    │  [Step 3/4] Capture Photo        │
                    │                                  │
                    │  ┌────────────────────────────┐ │
                    │  │                            │ │
                    │  │      [📷 Open Camera]      │ │
                    │  │                            │ │
                    │  │   or Tap to Upload Image   │ │
                    │  │                            │ │
                    │  └────────────────────────────┘ │
                    │                                  │
                    │  ⚠️ Photo must clearly show    │
                    │     odometer reading            │
                    │                                  │
                    │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
                    │                                  │
                    │  [Step 4/4] Verify Location      │
                    │                                  │
                    │  📍 Current Location:            │
                    │  22.5726° N, 88.3639° E          │
                    │                                  │
                    │  Branch: Kolkata-1               │
                    │  ✅ Within geofence (45m)       │
                    │                                  │
                    │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
                    │                                  │
                    │  ┌────────────┐  ┌────────────┐ │
                    │  │  Cancel    │  │   Submit   │ │
                    │  └────────────┘  └────────────┘ │
                    │                                  │
                    └──────────────────────────────────┘
```

### Component Specifications

#### Step 1: Type Selection [TOGGLE-TYPE-001]
```
Component: Button Toggle Group
Options: IN | OUT
Default: Last opposite type (if last was IN, default to OUT)
Behavior: Single selection, highlights selected option
Validation: Required, must select one
```

#### Step 2: Odometer Input [INPUT-ODOM-001]
```
Component: Number Input
Format: Whole numbers with comma separator (12,456)
Min Value: Last reading + 1
Max Value: Last reading + 500 (prevents typos)
Validation:
  - Must be greater than last reading
  - Cannot exceed max daily limit (500 KM)
  - Shows real-time distance calculation
Behavior:
  - Auto-calculate distance on blur
  - Show green checkmark if valid
  - Show red X if invalid with error message
```

**Auto-Calculation Display:**
```
Last Reading: 12,345 KM (IN, Nov 10)
New Reading: 12,456 KM
Distance: 111 KM ✓
Estimated Reimbursement: ₹ 750
```

#### Step 3: Photo Capture [INPUT-PHOTO-001]
```
Component: File Upload / Camera Capture
Options:
  1. [📷 Open Camera] - Direct camera access (mobile)
  2. [📁 Upload File] - File picker (desktop/mobile)

Constraints:
  - Max file size: 5 MB
  - Formats: JPG, JPEG, PNG
  - Minimum resolution: 640×480
  - Image compression on upload

Preview:
  - Show thumbnail after capture/upload
  - [X] Remove button to retake
  - Zoom on click to verify clarity

Validation:
  - Required field
  - Check for blur (future: AI validation)
  - Ensure metadata (EXIF) has timestamp
```

#### Step 4: Location Verification [VERIFY-LOC-001]
```
Component: Auto-fetched GPS + Geofence Check
Display:
  - Latitude, Longitude
  - Branch Name (matched)
  - Distance from branch center
  - Status: Within/Outside geofence

Geofence Logic:
  - Fetch user's assigned branch coordinates from DB
  - Calculate distance using Haversine formula
  - Configurable radius (default: 100 meters)
  - Allow/Block submission based on distance

States:
  ✅ Within geofence (Green) - Allow submission
  ⚠️ Outside geofence (Red) - Block with message:
     "You must be within 100m of your branch to submit reading"
  
Auto-refresh: Every 5 seconds if outside geofence
```

### Interaction Flow

```
1. User clicks "Submit Reading" on dashboard
   ↓
2. Modal opens → Check GPS permission
   ↓ (Denied)           ↓ (Granted)
3. Show permission   Fetch coordinates
   request dialog       ↓
                     4. Check geofence
                        ↓ (Outside)        ↓ (Inside)
                     Show error         Enable form
                        ↓
                     5. User fills type, reading, photo
                        ↓
                     6. Real-time validation checks
                        ↓ (All valid)
                     7. Submit button enabled
                        ↓
                     8. POST /api/readings/submit
                        ↓ (Success)        ↓ (Error)
                     Show success       Show error
                     toast              message
                        ↓                  ↓
                     Close modal        Stay in modal
                     Refresh dashboard  Allow corrections
```

### API Integration

```javascript
// POST /api/readings/submit
Request:
{
  "type": "out", // in | out
  "odometer_reading": 12456,
  "latitude": 22.5726,
  "longitude": 88.3639,
  "branch_id": 5,
  "photo_base64": "data:image/jpeg;base64,/9j/4AAQ...",
  "timestamp": "2025-11-11T10:30:00Z"
}

Success Response (201):
{
  "success": true,
  "message": "Reading submitted successfully",
  "reading_id": 789,
  "distance": 111,
  "estimated_amount": 750,
  "status": "pending_approval"
}

Error Responses:
{
  "success": false,
  "error_code": "GEOFENCE_VIOLATION",
  "message": "You are 250m away from branch. Please move closer."
}

{
  "success": false,
  "error_code": "INVALID_READING",
  "message": "Reading must be greater than last OUT reading (12,345 KM)"
}
```

### Validation Rules

| Field | Rule | Error Message |
|-------|------|---------------|
| Type | Required, IN or OUT | "Please select reading type" |
| Odometer | Must be > last reading | "Reading must be greater than {last_reading} KM" |
| Odometer | Cannot exceed last + 500 | "Daily travel cannot exceed 500 KM" |
| Photo | Required, max 5MB | "Photo is required and must be under 5MB" |
| Location | Within 100m geofence | "You must be near your branch to submit" |

### Responsive Behavior

**Desktop:**
- Modal: 600px width, centered
- 2-column layout for steps 1 & 4
- Camera opens in new window/tab

**Mobile:**
- Modal: Full screen
- Single column layout
- Native camera integration
- Touch-optimized buttons (min 44px height)

### Accessibility

- **Keyboard**: Tab through steps, Enter to submit
- **Screen Reader**: Announce each step, validation messages
- **ARIA**: `role="dialog"`, `aria-labelledby="modal-title"`
- **Focus Trap**: Keep focus within modal
- **ESC key**: Close modal with confirmation if data entered

---

## 4.4 Manager Approval Screen

**Screen ID**: APPR-MGR-001  
**Route**: /approvals  
**User Role**: Manager, Approver  
**Status**: 🟢