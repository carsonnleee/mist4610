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
<img width="1193" height="989" alt="ReadMe" src="https://github.com/user-attachments/assets/02b9b0c3-cf27-40f3-8996-7307a3ff877d" />


**Explanation:**  
Our data model is designed to represent the organizational structure of the Olympic Games, capturing the complex relationships among athletes, sports, events, teams, coaches, sponsors, and host locations. The Athlete entity serves as the central hub, linking competitors to their country, sport, coaches, sponsors, results, and team affiliations.

The Country entity stores information such as country name, continent, language, and population, and maintains one-to-many relationships with athletes, coaches, and teams. Each country may also host Olympic Games through the HostCity entity, which records the city name, population, climate, and associated country. Each HostCity can host multiple Games over time, with the Game table recording the year, season, start and end dates, and attendance.

The Sport entity organizes the types of competition (for example, swimming, track and field, or gymnastics). Each sport contains multiple Events, which specify individual competitions such as the 100m Dash or Women’s Balance Beam. Events are linked to their sport, game, and host city, and include additional context such as the number of competitors. Each event produces many Results, which record the athlete’s medal and rank, connecting each competitor’s performance directly to a specific event.

The Team and TeamMember entities represent group-based competition. Teams belong to a single country and have attributes such as name, type, and roster size, while TeamMember acts as an associative table that connects athletes to their teams and roles (for instance, “Relay Runner” or “Captain”).

To represent coaching relationships, the Coach entity stores details including gender and years of experience. The associative table CoachAssignment links coaches and athletes, allowing for a many-to-many relationship since one coach can train multiple athletes and one athlete can have multiple coaches.

Likewise, the Sponsor and Sponsorship entities model athlete endorsements. Sponsors include identifying details such as company name, country, and industry, while Sponsorship captures the partnership details — start and end dates, financial worth, and links to the athlete and sponsor.

Together, this schema accurately reflects the structure of the Olympic ecosystem. It supports queries such as total medals per country, athlete performance by sport, sponsorship value trends, or event participation across years and locations. Context-based attributes like event competitor counts, sponsorship worth, and coach experience years provide additional analytical depth for exploring the data.




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
