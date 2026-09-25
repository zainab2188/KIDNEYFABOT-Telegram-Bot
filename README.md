# KIDNEYFABOT — Interactive Health Education & Dialysis Care Telegram Bot 🤖🩺

## Overview
KIDNEYFABOT is a specialized, interactive Telegram bot developed in Python to assist hemodialysis patients and promote public kidney health literacy.

The bot transforms clinical nursing guidelines and educational materials into automated, user-friendly digital tools. It handles multi-step user workflows, dynamic Google Calendar URL generation, real-time nutrient checks, interactive quizzes, and automated PDF delivery.

---

## 🛠️ Key Features & Technical Capabilities

### 1. ⚖️ Interdialytic Fluid Weight Calculator (process_dry_weight & process_current_weight)
- Implements a multi-step conversation handler to calculate interdialytic fluid weight gain (comparing post-dialysis dry weight with current daily weight).
- Categorizes fluid retention risk levels into Safe (<=1.5kg), Moderate (1.5–2.5kg), and Critical/High Risk (>2.5kg), outputting instant clinical safety alerts.

### 2. 🥗 Interactive Nutritional & Electrolyte Guide (nutrition_guide)
- Uses Inline Keyboards (InlineKeyboardMarkup) to deliver real-time nutritional warnings regarding Potassium, Phosphorus, and Sodium levels in common foods (e.g., Bananas, Potatoes, Cheese, Apples, Dates).

### 3. 📅 Dynamic Google Calendar Appointment Scheduler (confirm_custom_schedule)
- Allows users to select custom dialysis treatment days (Saturday through Friday) using toggle buttons.
- Dynamically generates a encoded Google Calendar URL with recurring RRULE query parameters (FREQ=WEEKLY;BYDAY=...), enabling users to sync their medical schedule to their mobile devices with a single tap.

### 4. 📝 10-Question Health Literacy Quiz (QUIZ_QUESTIONS)
- Evaluates user knowledge regarding kidney function, hypertension, fluid intake, analgesics (painkiller) misuse, and dialysis mechanics.
- Uses callback query handlers (callback_query_handler) to track scores statefully in memory and generate automated performance badges.

### 5. 📋 Dialysis Session Checklist (send_dialysis_checklist)
- Provides a pre-session safety checklist verifying blood pressure medication, vascular access site care (AV Fistula / Catheter), and vital signs.

### 6. 📚 Automated PDF Booklet Distribution (send_pdf_booklet)
- Delivers the 8-page Arabic Educational Health Booklet directly within Telegram using asynchronous document streams.

---

## ⚠️ Medical & Scope Disclaimer
- Educational Prototype: Designed as a technical demonstration and health literacy solution for nursing and public health education.
- Clinical Supervision: All medical tracking features are intended for personal habit tracking and must be used under direct physician/nephrologist supervision.

---

## 💻 Tech Stack & Architecture
- Language: Python 3.x
- Framework/Library: pyTelegramBotAPI (telebot)
- Key Libraries: urllib.parse (URL Encoding for Calendar API), dotenv (Environment Variable Management for API Tokens).
- Architecture: Asynchronous Long-Polling Handler (infinity_polling).

