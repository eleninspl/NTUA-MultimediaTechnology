# MediaLab Assistant  
### Task Management System

---

## 📌 Overview

**MediaLab Assistant** is a Task Management System developed in **Java** using **JavaFX** for the graphical user interface and **JSON files** for persistent storage.  
It helps users organize and monitor their tasks efficiently, offering features like task creation, editing, deletion, searching, as well as management of categories, priority levels, and reminders.

---

## ✨ Features

### 📝 Task Management
- **Create Tasks**: Each task includes a title, description, category, priority, due date (without time), and status (`Open` by default).
- **Automatic Status Updates**: If the deadline has passed and the task isn't completed, its status changes to `Delayed`.
- **Edit/Delete Tasks**: Modify any task element or delete tasks. Deleting a task also removes all associated reminders.

### 🗂️ Category Management
- Add, rename, or delete categories.
- Default category `"No Category"` is protected and cannot be removed or edited.
- Deleting a category removes all associated tasks and updates reminders.

### 🔺 Priority Level Management
- Users can add, rename, or delete priority levels.
- A default `"Default"` priority exists and cannot be modified or removed.
- Tasks using a deleted priority are reassigned to `"Default"`.

### ⏰ Reminder Management
- Multiple reminders per task (1 day/week/month before, or a custom date).
- Reminders cannot be set for `Completed` tasks.
- Automatic validation ensures logical scheduling.
- Reminders are removed when task status becomes `Completed` or `Delayed`.

### 🔍 Task Search
- Search by combinations of title, category, and priority.
- Results show title, priority, category, and due date.

---

## 🧱 Project Structure

### 📦 Model Layer
Defines core data entities:
- `Task`, `Category`, `Priority`, `Reminder`
- Data is stored in:
  - `tasks.json`
  - `categories.json`
  - `priorities.json`
  - `reminders.json`

### ⚙️ Service Layer
Business logic:
- `TaskService`, `CategoryService`, `PriorityService`, `ReminderService`
- Responsible for CRUD operations and JSON I/O.

### 🧭 Controller Layer
Connects GUI with logic:
- `TaskController`, `CategoryController`, `PriorityController`, `ReminderController`
- Handles UI actions, updates views, manages user interactions.

---

## 📁 Data Storage (JSON)

- **categories.json** – Stores category objects (with unique ID and name).
- **priorities.json** – Stores priority levels including the protected `"Default"`.
- **tasks.json** – Stores task details (title, description, category, priority, due date, status).
- **reminders.json** – Stores reminders linked to tasks by ID and type/date.

---

## 🎨 GUI Overview

Built with **JavaFX**, the GUI is split into two main parts:

- **Top Section**: Displays aggregated task info (e.g., total tasks, completed, delayed, upcoming within 7 days).
- **Bottom Section**: Contains tabs for:
  - Tasks
  - Categories
  - Priorities
  - Reminders
  - Search  
Each tab has its own controller for managing interactions.

---

## 📌 Assumptions

- The `"No Category"` and `"Default"` priority cannot be modified or removed.
- Users cannot manually set a task as `Delayed`; it is handled automatically when the due date passes without completion.

---
