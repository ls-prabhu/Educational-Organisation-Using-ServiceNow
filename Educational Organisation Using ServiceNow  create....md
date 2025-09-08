# ⚙️ ServiceNow Setup Guide – Educational Management System

This guide explains how to set up the **Educational Organisation Project** on your **ServiceNow Personal Developer Instance (PDI)**.

---

## 🖥️ Prerequisites

1. Create a free account at [developer.servicenow.com](https://developer.servicenow.com)  
2. Request a **Personal Developer Instance (PDI)**  
3. Log in to your instance with **admin role**  

---

## 🛠️ Step 1: Create Tables

We will use **3 tables** for this project:

1. **Student Details (`u_student_details`)**
   - Admission Number (Auto-generated)  
   - Name  
   - DOB  
   - Address (Auto-filled from PIN Code)  
   - Status (New → InProgress → Joined/Rejected)

2. **Student Progress (`u_student_progress`)**
   - Student Reference (lookup to Student Details)  
   - Subject Marks  
   - Auto Total  
   - Auto Percentage  
   - Result (Pass/Fail)

3. **Sales Force (`u_sales_force`)**
   - Student Reference  
   - Course/Package  
   - Payment Info  
   - Follow-up Status  

👉 Navigate to **System Definition > Tables** → `New` → Create above tables.  

---

## 🛠️ Step 2: Design Forms & UI

- Go to each table → **Form Layout**  
- Add the fields as per requirements  
- Use **Form Sections** for clarity (e.g., Student Info, Address, Marks, Fees)  

---

## 🛠️ Step 3: Add Client Scripts & UI Policies

### Examples:
- **Auto Admission Number**  
  Client Script on `onLoad` → generate unique ID  

- **Auto-fill Address using PIN**  
  Script to fetch City/State based on PIN Code  

- **Student Progress Calculation**  
  Client Script `onChange` → Auto-calculate total, percentage, result  

---

## 🛠️ Step 4: Setup Workflows

- Create **Status Flow** in **Flow Designer**  
  - New → InProgress → Joined/Rejected  
- Add notifications if needed (optional)  

---

## 🛠️ Step 5: Role-based Access

- Currently **Admin** only  
- Future scope: Create roles for `Teacher`, `Parent`, `Sales`  

---

## 🛠️ Step 6: Import/Export with Update Sets

1. Navigate to → **System Update Sets > Retrieved Update Sets**  
2. **Import** the Update Set from `/UpdateSets/` folder  
3. **Commit** the set  
4. Modules available:  
   - `Admissions`  
   - `Student Progress`  
   - `Sales Force`  

---

## 🧪 Testing Checklist

- Student Admission Number auto-generated ✅  
- Address auto-filled from PIN ✅  
- Student Progress auto-total & percentage ✅  
- Status flow working correctly ✅  
- Sales Force linked to Students ✅  

---

## 🎯 You’re Done!

Now your **Educational Organisation System** is fully functional on ServiceNow 🚀
