# Mess Feedback Analysis System

A Java-based CLI application to gather hostel mess feedback from students and provide automatic analysis, trends, and alerts for mess management.

# Problem Statement

In a typical college hostel mess, feedback from students is collected either on paper, which is then ignored, or via WhatsApp groups, which is then forgotten. There is no efficient method to:
- Determine which meals are consistently rated low by students
- Detect a decline in the quality of food over a series of days
- Determine what the most common complaints are from the feedback provided by the students

This application addresses this problem by allowing for the efficient collection of feedback and automatically highlighting trends for the mess management to act on.

# Features

# Student
- Can submit feedback for any meal (Breakfast / Lunch / Snacks / Dinner)
- Can rate meal on scale of 1 to 5
- Can write comments on experience
- Can view history of submitted feedback

# Admin / Mess Manager
- Can view all feedback submitted
- Can view all feedback for specific meal types
- Can view analysis report for all feedback with:
  - Average ratings for each meal type (in stars too)
  - Overall average rating
  - What meal type performed best/worst
  - What are top keywords for all comments
  - What are top complaint keywords for all low-rated feedback
- Can export analysis report to .txt file
- Can view active alerts (meals with poor ratings)

## Project Structure

```
MessFeedbackSystem/
├── src/
│   ├── MealType.java          # Enum: BREAKFAST, LUNCH, SNACKS, DINNER
│   ├── Feedback.java          # Core data class with CSV serialization
│   ├── Alert.java             # Alert object with WARNING / CRITICAL severity
│   ├── FeedbackService.java   # Add, filter, sort feedback
│   ├── AnalysisService.java   # Averages, keyword analysis, report generation
│   ├── AlertService.java      # Consecutive day streak detection
│   ├── FileStorage.java       # Read/write feedback.csv and export report.txt
│   └── Main.java              # CLI entry point with student and admin menus
├── data/
│   ├── feedback.csv           # Auto-created on first run
│   └── weekly_report.txt      # Generated when admin exports report
└── README.md
```

## How to Run

```bash
# Compile
javac -d bin src/edu/ccrm/cli/MainMenu.java src/edu/ccrm/cli/CLIApp.java src/edu/ccrm/domain/*.java

# Run
java -cp bin edu.ccrm.cli.CLIApp
```

## Author

- Name: Mridul Hari tripathi
- ID: 24BAI10500
- Course: Programming in Java
- Institution: VIT Bhopal
