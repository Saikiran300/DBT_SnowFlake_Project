# ❄️ dbt + Snowflake Project: Session Summary Analytics

This project illustrates how to use **dbt** with **Snowflake** to build and test data models from raw user session logs. It involves constructing input models via CTEs, developing a session summary output model, configuring snapshots for historical tracking, and applying field-level tests to ensure data integrity.

---

## 📌 Project Summary

This project was developed using `dbt` and connected to a Snowflake warehouse. The main objective was to transform session-related user data into a summary model and apply testing and snapshotting for monitoring and validation.

---

## ✅ Tasks Completed

### 🔧 1. Project Initialization
- Set up a dbt project named `build_mau`
- Configured the Snowflake profile for deployment

### 🧱 2. Input Models
- Created two base models using **Common Table Expressions (CTEs)**:
  - `user_session_channel`
  - `session_timestamp`
- These serve as staging layers for session metadata and timestamps

### 📊 3. Output Model
- Created a final model: `session_summary`
- Performs joins between the input models
- Computes session duration and aggregates relevant fields

### 📸 4. Snapshot Configuration
- Implemented a snapshot for tracking changes in the `session_summary` table
- Uses the `timestamp` strategy with `session_end` as the change anchor

### 🧪 5. Data Testing
- Applied two dbt tests on the `session_id` field:
  - `unique`: Ensures each session_id appears only once
  - `not_null`: Validates no missing values exist for this key field

---

## 🧠 Technologies Used

- `dbt (Data Build Tool)`
- `Snowflake` Cloud Data Platform
- `Jinja SQL` (for dbt model templating)
- dbt's built-in **testing** and **snapshot** frameworks

---

## 📚 References

- [dbt Documentation](https://docs.getdbt.com/)
- [Snowflake Documentation](https://docs.snowflake.com/)
