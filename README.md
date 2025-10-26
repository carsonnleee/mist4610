# mist4610
# MIST 4610 – Group Project 1  
### Group Name: 15058_Group5
**Team Members:**  
- Carson Sams – @carsonnleee
- Lili Bennett – @bennettlili61342
- Hana Darley – @hanaldarley
- Ved Cholleti – @vedcho
- Mahtith Madasu – @mahithm1

---

## Scenario Description  

Our group chose to design a relational database focused on Olympic Games performance and participation data. The goal of this project is to model how the information about athletes, sports, events, and results is organized and analyzed across different Olympic years.
The purpose of our database is to allow users, such as analysts, national committees, and event organizers, to efficiently track athlete performance, medal outcomes, and country participation trends over time. The central entity in our model is the Athlete, representing each competitor participating in events across multiple Olympic Games. Each athlete competes on behalf of a country and is associated with various sports and events held in specific venues and host cities.
The database also captures details about teams, medals, and results, reflecting the multi-layered nature of Olympic competition. Our goal is to perform a series of analytical SQL queries to provide insight into Olympic operations and performance trends.
Through this model, users will be able to identify and analyze patterns such as medals won by each nation, athlete success across multiple Games, and performance efficiency of sports over time.

---

## Data Model  
**Image:**  
<img width="1185" height="949" alt="4610ProjectDM" src="https://github.com/user-attachments/assets/71ed6414-bf23-439c-a5a2-20ec87b2b052" />

**Explanation:**  
Our data model is based on the structure of the Olympic Games, and is designed to capture relationships among athletes, sports, events, teams, and host countries. The central entity in our model is the Athlete, which represents each competitor participating in various Olympic Games. Each athlete is connected to several key components, such as their country, sport, results, sponsors, and coaches.

The Country entity represents the nations participating in the Olympics and holds general information such as country name and continent. Each country can have many athletes, coaches, and teams associated with it, which is why we established one-to-many relationships from Country to Athlete, Coach, and Team.

The HostCity entity represents the location where each Olympic Games takes place. Each host city is connected to exactly one country (for example, Paris belongs to France), and each Olympic Game occurs in one host city. The Game entity stores information such as the year, season, start date, and end date of each Olympic competition. There is a one-to-many relationship between HostCity and Game, since a city could host multiple Games over time.

The Sport entity captures the broader categories of competition (such as swimming, gymnastics, or track and field). Each sport contains multiple Events, which represent the specific competitions within that sport — for example, the 100m Freestyle or Balance Beam. The Event table is related to both Sport and Game, showing when and where each event occurred.
Each Event produces many Results, one per athlete, which record medals, rankings, and scores. Because each result depends on both the athlete and the event, Result serves as an associative entity connecting them. This identifying relationship ensures that performance data is directly tied to both the individual competitor and the competition they participated in.

The Team entity represents national or event-specific teams, and the TeamMember table serves as a bridge between teams and athletes, allowing for a many-to-many relationship. For example, a single athlete might compete on a relay team and as an individual, while a team contains multiple athletes.

To reflect coaching assignments, the Coach entity stores information about each coach, including their name and associated country. Because a coach may train multiple athletes, and athletes can work with multiple coaches, we used an associative entity called CoachAssignment to manage this many-to-many relationship. Similarly, the Sponsor and Sponsorship tables represent business relationships between athletes and their sponsors, with Sponsorship serving as the non-identifying bridge that includes details such as sponsorship ID, athlete ID, and sponsor ID.

Overall, this model captures the essential structure and relationships within the Olympic Games. It allows users to query insights such as medal totals by country, athlete performance by sport, team composition, sponsorship trends, and event outcomes across different Games and host cities.



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
