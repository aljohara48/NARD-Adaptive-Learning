
NARD: AI-Driven Adaptive Educational Game for Children with Dyscalculia       


NARD is an adaptive educational iOS application designed to support children
aged 6–12 (Grades 1–6) with developmental dyscalculia.

The system combines **rule-based difficulty estimation** with
**Reinforcement Learning (Q-Learning)** to personalize mathematical practice
according to each learner's performance.

> NARD is an educational support tool and is not intended to diagnose dyscalculia.

---

## 🧠 Adaptive Learning Approach

### Rule-Based Difficulty Estimation
Each mathematical question is analyzed using four cognitive features:

- Symbolic Load (SL)
- Working Memory Load (WM)
- Operational Complexity (OP)
- Schema Complexity (SC)

These features are combined into a difficulty score and mapped into:

**Easy | Moderate | Hard**

### Reinforcement Learning
After the initial assessment, a **Q-Learning** model dynamically selects the
next question based on:

- Student grade
- Previous question difficulty
- Mathematical operation
- Answer correctness

Q-Learning parameters used in the project:

`α = 0.5` | `γ = 0.8` | `ε = 0.15`

---

## 📊 Dataset

NARD uses the public **Calc-asdiv_a** dataset developed by the MU-NLPC
research group.

- 1,218 math word problems
- Grades 1–6
- 8 original features
- CC BY-NC 4.0 license

The data pipeline included:

**Data Cleaning → EDA → Feature Extraction → Feature Engineering → Difficulty Scoring**

---

## 📈 Evaluation

The RL model was evaluated using simulated learner profiles and generated
interaction behavior.

Evaluation included:

- Cumulative and average reward
- Temporal-Difference error
- Regret
- Stability
- Mastery progression
- Baseline comparison

The adaptive Q-Learning strategy performed better than the evaluated
non-adaptive approaches, including random selection, fixed progression,
and static difficulty.

---

## 🏗️ System Architecture

- **Frontend:** SwiftUI / Xcode
- **Backend:** Google Cloud Run
- **Database:** Firebase Firestore
- **Adaptive Model:** Q-Learning
- **UI Design:** Figma
- **Version Control:** GitHub

Firebase stores student profiles, questions, answers, progress records,
and individual Q-tables, allowing each learner's adaptive state to persist
across sessions.

---

## 📱 Key Features

- Arabic RTL interface
- Multiple child profiles
- Grade-based initial assessment
- Adaptive question selection
- Level progression
- Student progress tracking
- Parent dashboard
- Progress report export

---

## 🎓 Academic Project

Graduation Project – BSc Data Science & Analysis  
Princess Nourah bint Abdulrahman University

**Team:**  
Aljawharah Abdulrahman Bin Omran  
Joudy Abdulmalik Althumayri  
Ghaidaa Mohammed Alqahtani  
Raghad Yasir Ababtain  
Leen Abdulaziz Alharbi  

**Supervisor:** Dr. Fatma Sulaiman Alrayes

---

## ⚠️ Limitations

The reinforcement learning model was primarily evaluated using simulated
learner profiles and has not yet been validated with a large real-world
sample of children with developmental dyscalculia.
