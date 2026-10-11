# NARD – Adaptive Educational Game for Children with Developmental Dyscalculia

NARD is an adaptive educational game designed to support children aged 6–12
(Grades 1–6) with developmental dyscalculia.

The system combines rule-based difficulty estimation with Reinforcement Learning
to provide a personalized mathematics learning experience that adapts to each
learner's performance.

> **Note:** NARD is a supportive educational tool and is not intended to diagnose
> dyscalculia. Diagnosis should be conducted by qualified teachers, specialists,
> or clinicians.

---

## 🎯 Project Overview

Children with developmental dyscalculia may experience difficulties with numerical
processing, arithmetic reasoning, working memory, and basic mathematical operations.

NARD was developed to provide an engaging and personalized learning environment
instead of relying on fixed difficulty levels.

The system:

- Organizes mathematical questions into structured difficulty levels.
- Adapts question selection based on the learner's performance.
- Tracks individual progress across learning sessions.
- Provides a child-friendly Arabic user interface.
- Allows parents to monitor student progress through a dashboard.

---

## 🧠 Adaptive Learning Approach

NARD uses a hybrid adaptive-learning approach consisting of two main components.

### 1. Rule-Based Difficulty Estimation

Mathematical questions are analyzed using four cognitive features:

- **Symbolic Load (SL)**
- **Working Memory Load (WM)**
- **Operational Complexity (OP)**
- **Schema Complexity (SC)**

These features are combined into a difficulty score that assigns each question
to one of three difficulty levels:

- Easy
- Moderate
- Hard

This creates an interpretable and structured question pool before adaptive
learning begins.

### 2. Reinforcement Learning

After the initial stage, NARD uses **Q-Learning** to dynamically adapt question
selection according to the learner's performance.

The learning state considers information such as:

- Academic grade
- Previous/current question difficulty
- Mathematical operation type
- Answer correctness

Each student interaction updates the Q-table, allowing the system to continuously
refine its question-selection strategy.

The Q-Learning configuration used in the project includes:

- Learning rate (α): **0.5**
- Discount factor (γ): **0.8**
- Exploration rate (ε): **0.15**

---

## 📊 Dataset

The project uses the public **Calc-asdiv_a** dataset developed by the MU-NLPC
research group and hosted on Hugging Face.

The dataset contains:

- **1,218 mathematical word problems**
- Primary-school questions from **Grades 1–6**
- **8 original fields**
- English arithmetic word problems from multiple open educational sources

Original dataset attributes include:

`id`, `question`, `chain`, `result`, `result_float`,
`result_unit`, `grade`, and `source_question`

The dataset was processed through:

- Data quality verification
- Missing-value handling
- Duplicate checking
- Text normalization
- Exploratory Data Analysis (EDA)
- Feature extraction
- Feature engineering
- Difficulty-score generation

The dataset is released under the **CC BY-NC 4.0** license.

---

## 📈 Evaluation

The Reinforcement Learning component was evaluated using simulated learner
profiles and generated interaction behavior before future validation with
real students.

Evaluation considered metrics including:

- Cumulative reward
- Average reward
- Temporal-Difference error
- Regret
- Stability
- Mastery progression
- Comparison with baseline policies

The evaluation showed that the adaptive Q-Learning approach improved its
decision-making behavior over time and performed better than the evaluated
non-adaptive strategies, including:

- Random question selection
- Fixed progression
- Static difficulty

---

## 📱 Application Features

The deployed iOS application includes:

- User authentication
- Child profile management
- Multiple child profiles under one parent account
- Grade selection
- Initial assessment
- Adaptive question delivery
- Level progression
- Correct and incorrect answer feedback
- Progress tracking
- Parent dashboard
- Student progress report export
- Arabic right-to-left interface
- Persistent learning progress across sessions

---

## 🏗️ System Architecture

NARD follows a client-server architecture.

### iOS Application
Built using **SwiftUI** in **Xcode**.

### Backend
Backend services are deployed using **Google Cloud Run** and handle:

- Initial assessment question selection
- Rule-based difficulty logic
- Q-Learning updates
- Adaptive next-question selection

### Database
**Firebase Firestore** stores:

- User accounts
- Child profiles
- Questions
- Student answers
- Progress records
- Q-Learning tables

Each learner maintains an individual learning state that can be preserved
and updated across sessions.

---

## 🛠️ Technologies

- Swift
- SwiftUI
- Xcode
- Python
- Reinforcement Learning
- Q-Learning
- Firebase Firestore
- Google Cloud Run
- Figma
- Git / GitHub
- Data Analysis
- Exploratory Data Analysis
- Feature Engineering

---

## 🔄 System Workflow

1. The learner selects their profile and grade.
2. Initial questions are selected according to the learner's academic grade.
3. The learner answers a mathematical question.
4. Interaction data is stored in Firebase Firestore.
5. The backend processes the learner's current state.
6. The Q-Learning model updates the learner's Q-table.
7. The system selects the next suitable question.
8. The learning cycle continues and adapts over time.

---

## 🎓 Academic Project

NARD was developed as a graduation project for the:

**Bachelor of Science in Data Science & Analysis**  
College of Computer and Information Sciences  
Princess Nourah bint Abdulrahman University

### Project Team

- Aljawharah Abdulrahman Bin Omran
- Joudy Abdulmalik Althumayri
- Ghaidaa Mohammed Alqahtani
- Raghad Yasir Ababtain
- Leen Abdulaziz Alharbi

**Supervisor:** Dr. Fatma Sulaiman Alrayes

---

## ⚠️ Limitations

The current project has several limitations:

- The system has not yet been validated with a large group of children diagnosed
  with developmental dyscalculia.
- Reinforcement Learning evaluation primarily used simulated learner profiles.
- The question dataset is relatively limited in size.
- The dataset contains English mathematical word problems and may not fully
  represent Arabic-speaking learners or the Saudi primary-school curriculum.

Future development can include real-world student testing, a larger Arabic
question bank, richer learning analytics, and further personalization.

---

## 📌 Project Status

Functional academic prototype developed and evaluated as a graduation project.
