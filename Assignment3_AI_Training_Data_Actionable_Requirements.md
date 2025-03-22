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