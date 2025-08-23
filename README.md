# ServiceNow List Views & Roles — Step‑by‑Step Guide

## Table of Contents

* [Key Concepts (Roles, Groups, Inheritance)](#key-concepts-roles-groups-inheritance)
* [Today’s Objective](#todays-objective)
* [List Controls & Context Menus](#list-controls--context-menus)

  * [A) List Control Menu (hamburger)](#a-list-control-menu-hamburger)
  * [B) Column Options Menu (three dots / right‑click column)](#b-column-options-menu-three-dots--rightclick-column)
  * [C) Row/Record Context Menu (right‑click a row)](#c-rowrecord-context-menu-rightclick-a-row)
* [Filtering with the Condition Builder](#filtering-with-the-condition-builder)

  * [Example 1: Caller = Rob Phillips](#example-1-caller--rob-phillips)
  * [Example 2: Stale & Unresolved incidents (30+ days)](#example-2-stale--unresolved-incidents-30-days)
* [Inline Editing (Single & Multi‑row)](#inline-editing-single--multirow)
* [Configure → List Layout (Views & Dot‑Walking)](#configure--list-layout-views--dotwalking)

  * [⚠️ Changing the Default View affects everyone](#️-changing-the-default-view-affects-everyone)
  * [Create a new, safe custom view (e.g., `itil view`)](#create-a-new-safe-custom-view-eg-itil-view)
  * [Assign a view to a role (System UI → Views)](#assign-a-view-to-a-role-system-ui--views)
  * [Impersonate to verify](#impersonate-to-verify)
* [Class Activity (Step‑by‑Step)](#class-activity-stepbystep)
* [Reference Fields & Dot‑Walking — Quick Primer](#reference-fields--dotwalking--quick-primer)
* [Quick Review / Knowledge Check](#quick-review--knowledge-check)

---

## Key Concepts (Roles, Groups, Inheritance)

* **Roles** define what a user **can/cannot access** in the platform.
* **Groups** can have roles. **Users inherit** all roles from the groups they belong to.
* **Users can also be given roles directly.** (Possible, though not best practice.)
* **Removing a role from a group affects *all* users** in that group/department.

---

## Today’s Objective

Understand the options available on a **list** page (not just *Incident*), including:

* List‑level, column‑level, and row‑level context menus
* Filtering via the **Condition Builder** (funnel)
* Configuring **views**, using **List Layout**, and **dot‑walking**

---

## List Controls & Context Menus

### A) List Control Menu (hamburger)

1. Open any list (e.g., **Incidents**).
2. Click the **three horizontal lines**, **List Control Menu** (hamburger) at the top left of the list **or** right‑click the **gray header**. <br> ![](https://github.com/CodeWithLuwam/July-1-Forms-and-List/blob/main/Images/List%20Control%20Menu%20(hamburger).png?raw=true) ![](https://github.com/CodeWithLuwam/July-1-Forms-and-List/blob/main/Images/Gray%20Header.png?raw=true)
3. Explore key sections: **View**, **Filters**, **Group By**, etc.

   * **View**: switch between pre‑built views.
   * **Filters**: open/adjust filter conditions for the whole list.
   * **Group By**: group results by any field.

### B) Column Options Menu (three dots / right‑click column)

1. On any column header, click the **three dots** **or** right‑click the header. <br> ![](https://github.com/CodeWithLuwam/July-1-Forms-and-List/blob/main/Images/Column%20Option%20Menu.png?raw=true)
2. Use column‑specific actions (e.g., **Sort A→Z**, **Sort Z→A**).

   * This menu is **column‑specific**, not list‑wide.

### C) Row/Record Context Menu (right‑click a row)

1. Right‑click a **specific record/row** to see actions that apply to that record, this is called **Record Context Menu**. <br>
![](https://github.com/CodeWithLuwam/July-1-Forms-and-List/blob/main/Images/Record%20Context%20Menu.png?raw=true)

---

## Filtering with the Condition Builder

1. Click the **funnel icon** (Filter) to open the **Condition Builder**.
2. Build conditions with three parts:

   * **Field** (column to filter on)
   * **Operator** (how to compare)
   * **Value** (what to match)
3. Click **Run** to apply.

### Example 1: Caller = Rob Phillips

1. Open the **Filter**.
2. **Field**: select **Caller**.
3. **Operator**: choose an appropriate operator (e.g., `is`, `starts with`, or `contains`).
4. **Value**: type `Rob` (or the full name `Rob Phillips`).
5. Click **Run**.

   * If a lookup pop‑out appears, select **Rob Phillips** to complete the filter.

### Example 2: Stale & Unresolved incidents (30+ days)

1. Open the **Filter**.
2. Add condition: **Updated** **is before** *(30 days ago)*.
3. Add condition: **State** **is not** `Resolved`.
4. Click **Run** to find incidents that may be forgotten and still open.

---

## Inline Editing (Single & Multi‑row)

* **Single value:** Double‑click a field in the list to edit directly. <br> ![](https://github.com/CodeWithLuwam/July-1-Forms-and-List/blob/main/Images/Single%20Row%20Inline%20Editing.png?raw=true)
* **Multiple rows (same column):**

  1. **Shift‑drag** to highlight cells in one column across multiple rows.
  2. **Double‑click** one of the highlighted cells to set the same value for all. <br> ![](https://github.com/CodeWithLuwam/July-1-Forms-and-List/blob/main/Images/Multiple%20Rows%20Inline%20Editing%20.png?raw=true)

---

## Configure → List Layout (Views & Dot‑Walking)

1. On any column header, right‑click → **Configure → List Layout**.
2. The List Layout shows:

   * **Available** (left): fields for the current table/form context.
   * **Selected** (right): fields currently shown in the view.
3. Use the arrows (or double‑click) to **add/remove fields**. Use **Up/Down** to **reorder**.
4. **Dot‑Walking (to other tables):**

   * In **Available**, some entries are **green with a plus (+)**. Click to **expand**.
   * Click the middle **dot‑walk** button (tree/graph icon) to browse fields from the referenced table.
   * Example: **Caller → Email** to show the Caller’s email in the Incident list.

### ⚠️ Changing the Default View affects everyone

* Editing the **Default** view updates it **system‑wide** for all users. Use with caution.

### Create a new, safe custom view (e.g., `itil view`)

1. **Configure → List Layout**.
2. In the **View name** dropdown, choose **New…**.
3. Name it (e.g., **`itil view`**) and configure the fields/order you need.
4. Save. A small **dot** on the view icon indicates you’ve personalized it.
5. You can **Reset to column defaults** later if needed.

### Assign a view to a role (System UI → Views)

1. Go to **All** → search **System UI → Views**.
2. Find and open your view record (e.g., **`itil view`**).
3. In **Roles**, click the **edit/pencil** icon and **add** the role(s) who should see this view by default.
4. Save.

### Impersonate to verify

1. Use the user menu → **Impersonate User**.
2. Choose an **ITIL** user.
3. Open the Incident list and confirm the **new view** appears/behaves as expected.

---

## Class Activity (Step‑by‑Step)

**Scenario:** Agents want a list that shows only the basics, in this order: `Number, Short Description, Priority, State, Caller, Email`.

1. **Open Incident list** → right‑click a column → **Configure → List Layout**.
2. **Remove** unneeded fields from **Selected**; **add** the required ones in this exact order:

   1. Number  2) Short Description  3) Priority  4) State  5) Caller  6) Email
3. **Dot‑Walk** to get **Caller → Email** if it’s not in Available.
4. (Demonstration of impact) Save this in the **Default** view to see system‑wide effect.
5. **Impersonate** a user **without** `itil` to confirm they also see it (shows why Default is risky).
6. **Set it back** to the prior Default (or **Reset to column defaults**).
7. **Create a new view** named **`itil view`** and configure it to match the requested order.
8. **System UI → Views**: open **`itil view`**, add the **`itil`** role to the view’s Roles.
9. **Impersonate** an **ITIL** user to confirm the layout/view is available and correct.

---

## Reference Fields & Dot‑Walking — Quick Primer

* A **reference field** points to a record in **another table** (e.g., **Caller** on Incident references the **User** table).
* Icons like the **magnifying glass** open a lookup to that other table.
* **Dot‑Walking** lets you display fields from the referenced record (e.g., `Caller.Email`) in your list view **without duplicating data**.

---

## Quick Review / Knowledge Check

1. **What does a user see when they open a list?**

   * The **Default view**, unless a **custom view** is assigned to their **role**.
2. **What are the 3 components of a filter condition?**

   * **Field**, **Operator**, **Value**.
3. **What is the List Layout and when should we use it?**

   * The **List Layout** is where you **customize** which fields appear (and in what order) for a list **view**, and where you can **dot‑walk** to referenced data.

---

### Cheatsheet

* **List control menu:** hamburger or right‑click header → list‑wide actions.
* **Column menu:** three dots or right‑click column → column‑specific actions.
* **Row menu:** right‑click a record → row‑specific actions.
* **Filter:** funnel → Field + Operator + Value → Run.
* **Inline edit:** double‑click; multi‑edit with **Shift‑drag**.
* **Configure → List Layout:** add/remove/reorder fields; **dot‑walk** to referenced fields.
* **Views:** create new (safe), assign to **roles** via **System UI → Views**.
