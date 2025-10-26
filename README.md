# mist4610
# MIST 4610 – Group Project 1  
### Group Name: 15058_Group5
**Team Members:**  
- Carson Sams – [@carsonnleee] (https://github.com/carsonnleee)
- Lili Bennett – [@bennettlili61342] (https://github.com/bennettlili61342)
- Hana Darley – [@hanaldarley] (https://github.com/hanaldarley)
- Ved Cholleti – [@vedcho] (https://github.com/vedcho)
- Mahtith Madasu – [@mahithm1] (https://github.com/mahithm1)

---

## Scenario Description  

Our group chose to design a relational database focused on Olympic Games performance and participation data. The goal of this project is to model how the information about athletes, sports, events, and results is organized and analyzed across different Olympic years.
The purpose of our database is to allow users, such as analysts, national committees, and event organizers, to efficiently track athlete performance, medal outcomes, and country participation trends over time. The central entity in our model is the Athlete, representing each competitor participating in events across multiple Olympic Games. Each athlete competes on behalf of a country and is associated with various sports and events held in specific venues and host cities.
The database also captures details about teams, medals, and results, reflecting the multi-layered nature of Olympic competition. Our goal is to perform a series of analytical SQL queries to provide insight into Olympic operations and performance trends.
Through this model, users will be able to identify and analyze patterns such as medals won by each nation, athlete success across multiple Games, and performance efficiency of sports over time.

---

## Data Model  
**Image:**  
<img width="1193" height="989" alt="ReadMe" src="https://github.com/user-attachments/assets/12d8c76d-3f61-4c52-b50b-901f197b5cd3" />


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


<!-- 2:12:25 PM -->
<img width="555" height="467" alt="Screenshot 2025-10-26 at 2 12 25 PM" src="https://github.com/user-attachments/assets/4b96d263-1625-434d-8846-2b5914cf2125" />

<br/>

<!-- 2:13:06 PM -->
<img width="411" height="545" alt="Screenshot 2025-10-26 at 2 13 06 PM" src="https://github.com/user-attachments/assets/f6c389cd-41cf-4968-97b6-71308e0d724c" />

<br/>

<!-- 2:13:20 PM -->
<img width="420" height="532" alt="Screenshot 2025-10-26 at 2 13 20 PM" src="https://github.com/user-attachments/assets/70ff9c0e-a873-48e1-bdff-97874230c864" />

<br/>

<!-- 2:13:33 PM -->
<img width="414" height="330" alt="Screenshot 2025-10-26 at 2 13 33 PM" src="https://github.com/user-attachments/assets/45b950b3-44f8-4c20-83fa-9f051cd376e5" />

<br/>

<!-- 2:13:42 PM -->
<img width="420" height="542" alt="Screenshot 2025-10-26 at 2 13 42 PM" src="https://github.com/user-attachments/assets/0b52b6de-dc9a-45d0-af91-5276d129c536" />

<br/>

<!-- 2:13:56 PM -->
<img width="416" height="517" alt="Screenshot 2025-10-26 at 2 13 56 PM" src="https://github.com/user-attachments/assets/1d6d306d-dc47-40dc-9930-0392a3da612c" />

<br/>

<!-- 2:14:05 PM -->
<img width="435" height="525" alt="Screenshot 2025-10-26 at 2 14 05 PM" src="https://github.com/user-attachments/assets/21602804-a5b6-4083-8763-9154f575104b" />

<br/>

<!-- 2:14:17 PM -->
<img width="445" height="197" alt="Screenshot 2025-10-26 at 2 14 17 PM" src="https://github.com/user-attachments/assets/3c589d43-c1a2-4243-a947-ab79553b42d2" />



## Database Information  
**Database Name:** ns_F25MIST4610_15058_Group5 

**Important Note:** Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Qx(where x is to be replaced by the query number)

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
