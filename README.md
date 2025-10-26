# mist4610
# MIST 4610 – Group Project 1  
### Group Name: 15058_Group5
**Team Members:**  
- Carson Sams – [@carsonnleee](https://github.com/carsonnleee)  
- Lili Bennett – [@bennettlili61342](https://github.com/bennettlili61342)  
- Hana Darley – [@hanaldarley](https://github.com/hanaldarley)  
- Ved Cholleti – [@vedcho](https://github.com/vedcho)  
- Mahith Madasu – [@mahithm1](https://github.com/mahithm1)

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

<img width="411" height="278" alt="Screenshot 2025-10-26 at 7 40 50 PM" src="https://github.com/user-attachments/assets/602f3d81-3537-4ed4-83c8-d055ade41dcb" />

1. Query 1 lists the total number of medals won by each country, while excluding countries that competed as part of a team. The query joins together the Country, Athlete, and Result tables in order to count the number of medals associated with each country’s athletes. A subquery ensure that only countries without team associations are included. The results are then grouped by country and ordered in descending order of total medals won.

Query 1 allows managers and analysts to quickly see which countries are the most successful in terms of medal counts when considering only individual athletes (which excludes team-based results. This information is useful for evaluating the performance of athletes on a country-by-country basis and for identifying standout nations in individual competitions. By presenting the results in descending order, it becomes immediately clear which countries are leading. This makes it easier for Olympic committees, sports analysts, or broadcasters to highlight top-performing nations in individual events. 

<img width="730" height="488" alt="Screenshot 2025-10-26 at 6 23 35 PM" src="https://github.com/user-attachments/assets/4b0d406b-c93a-4651-a4b0-5b86293d273f" />


2. Query 2 lists the sponsors and the athletes they support, but only for countries located in North America. The query retrieves the sponsor’s name, the athletes first and last name, and the athlete’s country by joining together the Sponsor, Sponsorship, Athlete, and Country tables. A filter ensures that only athletes from the specified North American countries are included in the results. The output is ordered first by the sponsor’s name and then alphabetically by the athlete’s last name.

Query 2 allows managers and analysts to identify which sponsors are actively supporting athletes in North America and the specific athletes who benefit from those sponsorships. This information is useful for both sponsors and Olympic committees, as it highlights sponsorship patterns and shows which brands have the strongest presence in a North American market. It also makes it easier to see if certain athletes or countries are attracting more sponsorship interest, which can inform marketing strategies, partnership opportunities, or resource allocation. By ordering the results by sponsor and athlete, the query presents the data in an easy to navigate fashion. 

3. Query 3 lists all athletes who are currently active along with the sport they participate in. The query uses the Athlete and Sport tables, joining them on the sportID. It concatenates the athlete’s first and last names into a single field labeled as AthleteName and pairs this with the name of their sport. A filter ensures that only athletes with an Active status are included, and the results are ordered alphabetically by athlete name. 

Query 3 allows managers, coaches, and analysts to quickly see which athletes are currently active across all sports. This is particularly useful for keeping track of eligible athletes for upcoming competitions, as well as for managing training schedules, sponsorships, and event planning. By focusing only on active athletes, the query eliminates outdated or irrelevant records (ex. Retired or inactive athletes), ensuring that the results reflect the current competitive landscape. Listing athletes in alphabetical order makes the data easy to scan and reference. 

4. Query 4 lists all sports whose name contain either the word ‘ball’ or ‘swim’ and shows the number of athletes participating in each. The query uses the Sport table and joins it with the Athlete table to count how many athletes are linked to each sport. A REGEXP filter ensures that only sports with names containing ‘ball’ or ‘swim’ are included. The results are grouped by sport name and ordered in descending order of athlete count.

Query 4 allows managers and analysts to focus specifically on certain categories of sports, specifically ball-related and swimming related disciplines, to see which have the highest athlete participation. This can be particularly useful for identifying popular sports that may require additional resources, coaching staff, or facilities due to higher athlete engagement. Conversely, it also highlights sports with fewer participants, which may indicate areas for potential growth and recruitment. By ordering the results from the highest to lowest athlete count, the query makes it easy to prioritize attention toward the most heavily represented sports first. 

5. Query 5 counts the number of athletes per sport, per year, and per country. The query joins together multiple tables (Athlete, Country, Result, Event, Game, and Sport) to provide detailed breakdowns of athlete participation. It counts distinct athlete IDs to avoid duplicates and groups the results by sport, the year of the Olympic Games, and the country name. Finally, the output is ordered in descending order of athlete counts, with results showing the most heavily represented sports, years, and countries at the top. 

Query 5 allows managers, organizers, and analysts to examine patterns of athlete participation across sports, years, and countries. This information is valuable for identifying which countries have historically contributed the most athletes to specific sports in particular Olympic years. It can highlight growth or decline in participation for certain sports over time, as well as which nations are consistently strong contributors. Ordering the results by athlete count helps prioritize attention to the largest representations, making it easier to spot key trends in global Olympic participation. 

6. Query 6 finds the number of medals won by countries during the years in which they hosted the Olympic Games. The query joins together the Country, HostCity, Game, Event, Result, and Athlete tables to connect host nations with their athletes medal results. It groups the results by both the country name and the Olympic year, and then counts the total medals earned. The output is ordered by Olympic year, and then by total medals in descending order.

Query 6 allows managers, analysts, and Olympic historians to evaluate how host countries perform in their own Olympic Games. This information is particularly useful for studying the ‘home advantage’, where athletes may have an edge when competing in familiar landscapes with strong local support. It also provides insights into how well host nations capitalize on the opportunity to showcase their athletic talent during the Games. By grouping results by both year and country, the query makes it possible to compare different host nations across Olympic years, while the descending order of medal counts highlights the most successful hosting performances first. 

7. Query 7 calculates the average sponsorship worth per team and the unique number of sponsors supporting each team. The query joins together the Team, TeamMember, Athlete, Sponsorship, and Sponsor tables to connect teams with their athletes and associated sponsorships. It computes the average sponsorship value (AvgSponsorshipWorth) and counts the distinct sponsors per team (NumberOfSponsors). The results are grouped by team name and displayed in descending order of average sponsorship worth. 

Query 7 allows managers and analysts to evaluate the financial backing that different teams receive through sponsorships. This is useful for identifying which teams have the highest-value sponsorship deals and which may have less financial support. Understanding average sponsorship worth helps highlight where the largest commercial investments are being made, while counting the number of sponsors per team provides insight into the breadth of sponsor interest. By sorting results from highest to lowest average sponsorship worth, this query prioritizes teams that are most financially supported, which offers valuable information for sports organizations, marketers, and Olympic committees. 

8. Query 8 identifies Olympic events that had more than 10 competitors, showing the number of competitors in each, and the number of medals awarded per Olympic year. The query joins the Event, Sport, Game, and Result tables, filtering to only include events with more than 10 participants and at least one medal awarded. It groups results by event name, sport, game year, competitor count, then counts the medals awarded. The results are ordered in descending order first by number of competitors, then by medals awarded.

Query 8 allows managers, analysts, and organizers to examine large-scale events with significant athlete participation and track how many medals were awarded in those competitions. This is useful for identifying which events attract the most athletes, which can help planning logistics such as scheduling, facilities, and media coverage. It also highlights the balance between the size of the competition, and the number of medals available, offering insights into event competitiveness. Sorting the results by the highest competitor first ensures that the most demanding events are prioritized for review. 

9. Query 9 lists U.S athletes who are currently active, and have won two or more medals. For each qualifying athlete, the query shows their sport, their current sponsor, and the total sponsorship worth provided by that sponsor. It first uses a subquery to identify athletes with at least two medals, then calculates sponsorship details by summing the sponsorship worth for each athlete’s sponsor. The query joins together the Athlete, Country, Sport, Result, and Sponsorship tables, applying filters to only include athletes from the USA with an active status. The results are ordered by the number of medals won in descending order, then alphabetically by athlete name.

Query 9 allows managers, analysts, and sponsors to pinpoint top-performing U.S athletes who are both successful (with 2+ medals) and currently active in competition. This is especially valuable for sponsors and marketing teams, as it highlights which American athletes represent strong investment opportunities due to both their achievements and their ongoing participation. Olympic committees and analysts can also use this query to track standout U.S athletes and their commercial backing. Sorting the list by medal count ensures the most decorated athletes appear first, making it easy to prioritize them for attention, recognition, or sponsorship expansion. 

10. Query 10 lists all active athletes along with their sport, each Olympic year in which they recorded a result, and the athlete’s current age. The query Joins Athlete, Sport, Result, Event, Game, filters to Athlete.atheleteStatus = ‘Active, and computes age using YEAR(CURDATE()) - YEAR (Athlete.athleteDOB). Results are shown one row per athlete/game year, and are ordered by Olympic year, sport name, and athlete first name. 

Query 10 allows coaches and analysts to view the age profiles of currently active athletes by sport and by Olympic year in which they’ve competed. This helps with roster planning, identifying veterans v. younger athletes within each sport, and spotting age-related trends across recent Games. Ordering by year and sport makes it easy to scan a given Games edition and compare athletes within the same discipline. 
