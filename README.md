# mist4610
# MIST 4610 – Group Project 1  
### Group Name: [Enter your team name here]  
**Team Members:**  
- [Name 1] – [GitHub Link]  
- [Name 2] – [GitHub Link]  
- [Name 3] – [GitHub Link]  
- [Name 4] – [GitHub Link]
- [Name 5] – [GitHub Link]

---

## Scenario Description  
[Briefly describe your business scenario here. Example:  
“Our database is designed for a local coffee shop in Athens, GA to manage orders, inventory, employees, and customers.”]

---

## Data Model  
**Image:**  
![Data Model Diagram](./datamodel.png)

**Explanation:**  
[Explain key entities and relationships here in plain English. Example:  
“Each customer can place multiple orders, and each order is linked to one employee and multiple menu items.”]

---

## Data Dictionary  
[Include a short table or bullet list explaining key columns and data types. Example:]  
- **CustomerID** – INT, primary key, unique identifier for each customer  
- **OrderDate** – DATE, date when the order was placed  
- **Price** – DECIMAL(5,2), price of each item  

---

## Database Information  
**Database Name:** [Enter schema name here]  
**Tables:** [List table names here]  
**Rows per table:** Minimum 10  

---

## Queries  
| # | Query Description | Managerial Justification | SQL Features Used |
|---|--------------------|---------------------------|-------------------|
| 1 | [Describe what the query does] | [Why a manager would care] | [JOIN, GROUP BY, etc.] |
| 2 | ... | ... | ... |
| 3 | ... | ... | ... |
| ... | ... | ... | ... |

**Example SQL Snippet:**  
```sql
SELECT customerName, COUNT(orderID)
FROM Orders
GROUP BY customerName
HAVING COUNT(orderID) > 5;
