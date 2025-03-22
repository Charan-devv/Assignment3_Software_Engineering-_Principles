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