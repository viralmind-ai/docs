# 🪧 Demonstrations

The **core of the Training Gym** is the **demonstration system**, where users record themselves completing tasks so that AI can learn from **real human interactions**. Every demonstration is evaluated using **a grading system** that determines **reward payouts and AI training effectiveness**.

This ensures that **only high-quality demonstrations improve AI models**, while contributors are fairly **compensated in $VIRAL** based on their performance.

***

## **How Demonstrations Work?**

### 1. **Users Record Demonstrations**

* Contributors **perform a task on their computer** while the system records every action.
* The demonstration captures **clicks, keystrokes, UI navigation, and task execution**.
* The AI **observes and processes** how humans complete tasks.

📌 **Example:** A user records a demonstration of sending a Solana transaction using Phantom Wallet, navigating through wallet settings, entering recipient addresses, and confirming fees.

***

### 2. **Processing & Structuring Data for AI Training**

* After recording, users **process their demonstration** to structure it into **clear, repeatable steps** AI can learn from.
* AI models analyze **workflow sequences, decision-making logic, and UI interactions**, allowing them to **mimic human behavior efficiently**.
* Contributors can **review their submission** to ensure it’s accurate and useful.

📌 **Example:** The system learns to break the Solana transaction prompt into structured steps like **“Open Phantom Wallet,” “Enter Recipient Address,” “Review Gas Fees,” and “Confirm Transaction.”**

***

### 3. **Submission & Quality Review**

* Once processed, users **upload their demonstration** for AI training.
* Each submission is evaluated by **ViralMind’s data quality agent**, which grades it based on **clarity, accuracy, and effectiveness**.
* The **higher the quality, the better the AI learns and the greater the reward for the contributor**.

📌 **Example:** A well-structured Solana transaction demo receives an **85% quality rating**, qualifying for near-max rewards.

***

### **Grading System: How Demonstrations Are Scored**

Each uploaded demonstration is **scored by an AI-powered data quality agent**. The grading process evaluates the submission across multiple dimensions:

#### **🔹 1. Clarity & Step-by-Step Execution (40%)**

* Are the actions performed in **a clear, structured, and repeatable** way?
* Does the demonstration include **all necessary steps without skipping any?**
* Is the recording **free of unnecessary delays or misclicks?**

📌 **Example:** A contributor records a **clear**, step-by-step demonstration of sending crypto without extra delays → **High Score**

***

#### **🔹 2. Accuracy & Task Completion (30%)**

* Did the user **correctly complete the task** from start to finish?
* Is the workflow **accurate and applicable to real-world use?**
* Are **errors corrected quickly** without affecting the AI’s ability to learn?

📌 **Example:** A user enters a **wrong wallet address** but **fixes it immediately and completes the transaction successfully** → **Good Score**

📌 **Example:** A user **submits a demonstration with missing steps**, like forgetting to confirm a transaction → **Low Score**

***

#### **🔹 3. AI Training Usefulness (20%)**

* Is this demonstration **generalizable** so AI can apply it to different cases?
* Does it help the AI **recognize patterns in human decision-making?**
* Is it a **new, valuable contribution**, or a duplicate of an existing submission?

📌 **Example:** A **unique demonstration** of interacting with a complex UI workflow → **High Score**

📌 **Example:** A **duplicate of an existing task without meaningful variation** → **Low Score**

***

#### **🔹 4. Efficiency & Flow (10%)**

* Was the demonstration **efficiently completed** without unnecessary delays?
* Did the user **execute the task smoothly** without excessive hesitations?
* Was the workflow **consistent and optimized** for AI learning?

📌 **Example:** A user **executes a workflow quickly and effectively** without mistakes → **High Score**

📌 **Example:** A user **takes too long or has inconsistent actions**, making it hard for AI to learn → **Low Score**

***

### **Reward Payouts Based on Grading**

The **higher the quality of a demonstration, the higher the payout**.

| **Quality Score** | **Reward Payout** | **Notes**                                          |
| ----------------- | ----------------- | -------------------------------------------------- |
| **90-100%**       | **100% payout**   | Perfect execution, maximally useful AI training    |
| **80-89%**        | **85% payout**    | High quality, minor inefficiencies or small errors |
| **70-79%**        | **70% payout**    | Good submission, may need slight improvements      |
| **50-69%**        | **50% payout**    | Basic level, needs optimization                    |
| **Below 50%**     | **No payout**     | Poor quality, refunded to training pool            |

📌 **Example:**

A demonstration worth **$0.20 per submission** gets **graded at 85%**.

The worker **receives $0.17**, and **$0.03 is refunded to the training pool.**

📌 **Example:**

A low-quality demonstration **graded at 40%** receives **no reward**, and the **full $0.20 is refunded** to the pool for future high-quality submissions.

***

### **Dynamic Reward Pool Efficiency**

* **Unused funds from low-quality submissions are returned to the Gym’s training pool**, ensuring that AI **only learns from high-quality data**.
* This **incentivizes contributors to submit clear, structured, and useful demonstrations**, maximizing AI performance.
* **Gym owners can adjust reward structures**, increasing payouts to attract better contributors.

📌 **Example:** A Gym **not receiving enough high-quality submissions** increases its bid from **$0.20 per demo to $0.30**, bringing in more skilled trainers.
