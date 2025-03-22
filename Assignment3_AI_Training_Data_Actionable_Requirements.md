# Assignment 3: Actionable Items for AI Training System

## 🎯 Purpose
This document breaks down user requirements into separate, actionable GitHub tasks — each with its own assumptions, validation strategies, implementation strategies, and suggestions. The goal is to turn high-level needs into trackable and prioritized issues for development.

---

## 🔽 Task Priority Overview

| Priority  | User Requirement               | Justification                                              |
| --------- | ------------------------------ | ---------------------------------------------------------- |
| 🔴 High   | Categorized Training Questions | Critical for usability and organized data flow             |
| 🔴 High   | Separate Questions and Answers | Supports developer focus and core data structuring         |
| 🟡 Medium | Balanced Training Data         | Encourages fairer AI models but not critical to MVP        |
| 🟢 Low    | Reports on Data Balance        | Useful for audit and improvement, not immediately required |

---

##  User Requirement: Categorized Training Questions

**User Story:**  
*As an AI developer, I want training questions to be grouped by category so I can quickly find relevant data for model training.*

**Assumption:**  
Categorized questions help developers find relevant data faster.

**Validation Strategy:**  
- Interview developers to evaluate improvements in workflow.  
- Compare search times using categorized vs. uncategorized datasets.  

**Implementation Strategy:**  
- Extend the database schema to include a `category` field.  
- Design a user interface for selecting categories when adding questions.  
- Enable filtering of questions by category in the UI.  

### Implementation Strategy Sub-Issues
**Sub-Issue 1:** Implement Category Selection Component  
**Priority:** 🔴 High  
- **Goal:** Allow users to select categories while creating questions.  
- **Approach:** Build a dropdown or tag-based component using React.  
- **Tasks:**  
  - Design UI mockup for category tagging  
  - Implement reusable dropdown/tag selector  
  - Integrate component with question form  

  **Sub-Issue 2:** Enable Backend Storage for Categories  
**Priority:** 🔴 High  
- **Goal:** Persist category information when saving questions.  
- **Approach:** Update API and DB schema to support category field.  
- **Tasks:**  
  - Modify backend controller to accept category field  
  - Update DB model  
  - Test with sample data insertion 

  **Sub-Issue 3:** Filter Questions by Category (Frontend)  
**Priority:** 🔴 High  
- **Goal:** Allow users to view questions based on selected category.  
- **Approach:** Add category filter dropdown to UI.  
- **Tasks:**  
  - Build category filter UI  
  - Connect it to backend API  
  - Display filtered results dynamically  

  ### Implementation Suggestions

- Use dropdown or tag-based category input  
- Index the `category` column in the database for performance  
- Use standard CSS frameworks (e.g., Bootstrap) for UI consistency 

### Implementation Suggestions Sub-Issue

**Sub-Issue 4:** Optimize Category Queries in Database  
**Priority:** 🟠 Medium  
- **Goal:** Improve search performance for category-based queries.  
- **Approach:** Add indexing and optimize query performance.  
- **Tasks:**  
  - Add index to category column  
  - Analyze query performance before/after  
  - Refactor slow queries if needed  

---

##  User Requirement2: Separate Questions and Answers

**User Story:**  
*As an AI developer, I want questions stored separately from answers so I can think critically without being biased by the solution.*

**Assumption:**  
Separating questions and answers reduces bias and improves developer focus.

**Validation Strategy:**  
- Collect developer feedback on cognitive workflow.  
- Compare model performance using mixed vs. separated training sets.  

**Implementation Strategy:**  
- Create separate tables for questions and answers.  
- Add a toggle feature to reveal/hide answers.  
- Control answer visibility with user roles.

### Implementation Strategy Sub-Issues

**Sub-Issue 1:** Create Answer Table with Foreign Key Relationship  
**Priority:** 🔴 High  
- **Goal:** Separate questions and answers in the database schema.  
- **Approach:** Create a normalized table `training_answers` with a `question_id` FK.  
- **Tasks:**  
  - Design DB schema  
  - Implement using PostgreSQL  
  - Test table relationships 

  **Sub-Issue 2:** Design Toggle Component for Answer Visibility  
**Priority:** 🔴 High  
- **Goal:** Allow users to optionally reveal answers when needed.  
- **Approach:** Use React/Vue to implement toggle button.  
- **Tasks:**  
  - Add "Show/Hide Answer" toggle  
  - Set default to hidden  
  - Handle state transitions and UI feedback

  **Sub-Issue 3:** Secure Access to Answers Using RBAC  
**Priority:** 🟠 Medium  
- **Goal:** Restrict answer visibility to authorized users.  
- **Approach:** Implement role-based access on backend.  
- **Tasks:**  
  - Define user roles and permissions  
  - Enforce in route/middleware  
  - Test role restrictions 
  
### Implementation Suggestions

- Use foreign key `question_id` in the `training_answers` table  
- Add access logging when users reveal answers  
- Use React or Vue for toggle interactivity  

### Implementation Suggestions Sub-Issue

**Sub-Issue 4:** Log Answer View Events  
**Priority:** 🟢 Low  
- **Goal:** Track access to answer data.  
- **Approach:** Log timestamp and userID when answer is revealed.  
- **Tasks:**  
  - Create answer view log table  
  - Insert log on each toggle  
  - Create admin view for audit  
---

## User Requirement3: Balanced Training Data

**User Story:**  
*As an AI developer, I want to detect bias in my data so I can ensure my models are trained fairly.*

**Assumption:**  
Detecting and correcting bias improves AI model reliability.

**Validation Strategy:**  
- Compare model metrics before and after balancing datasets.  
- Ask developers if bias reports improved their dataset decisions.  

**Implementation Strategy:**  
- Integrate a fairness detection tool.  
- Visualize dataset imbalance.  
- Allow manual rebalancing before training. 

### Implementation Strategy Sub-Issues

**Sub-Issue 1:** Integrate Fairness Detection Library  
**Priority:** 🔴 High  
- **Goal:** Automatically flag imbalance in training data.  
- **Approach:** Use AIF360 or Fairlearn to scan for bias.  
- **Tasks:**  
  - Install and configure library  
  - Run tests on sample dataset  
  - Output basic bias metrics 

  **Sub-Issue 2:** Display Bias Summary in UI  
**Priority:** 🟠 Medium  
- **Goal:** Help developers visualize fairness issues.  
- **Approach:** Show visual stats like pie/bar charts.  
- **Tasks:**  
  - Integrate Chart.js  
  - Render balance summary view  
  - Test across user inputs 

  **Sub-Issue 3:** Add Parameter Tuning Controls for Dataset Rebalancing  
**Priority:** 🟠 Medium  
- **Goal:** Allow user to adjust imbalance before training.  
- **Approach:** Add UI sliders or checkboxes for control.  
- **Tasks:**  
  - Create filter control bar  
  - Adjust sampling or weighting logic  
  - Retest after adjustments 
---

## User Requirement4: Reports on Data Balance

**User Story:**  
*As an AI developer, I want reports on data balance so I can identify gaps and improve training quality.*

