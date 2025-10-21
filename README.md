# mist4610
# MIST 4610 – Group Project 1  
### Group Name: 15058_Group5
**Team Members:**  
- Carson Sams – @carsonnleee
- Lili Bennett – @bennettlili61342
- [Name 3] – [GitHub Link]  
- [Name 4] – [GitHub Link]
- [Name 5] – [GitHub Link]

---

## Scenario Description  

Our group chose to design a relational database focused on Olympic Games performance and participation data. The goal of this project is to model how information about athletes, sports, events, and results is organized and analyzed across different Olympic years.
The purpose of our database is to allow users, such as analysts, national committees, and event organizers, to efficiently track athlete performance, medal outcomes, and country participation trends over time. The central entity in our model is the Athlete, representing each competitor participating in events across multiple Olympic Games. Each athlete competes on behalf of a country and is associated with various sports and events held in specific venues and host cities.
The database also captures details about teams, medals, and results, reflecting the multi-layered nature of Olympic competition. Our goal is to perform a series of analytical SQL queries to provide valuable strategic insights into Olympic operations and performance trends.
Through this model, users will be able to identify and analyze patterns such as medals won by each nation, athlete success across multiple Games, and performance efficiency of sports over time.

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
