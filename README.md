# Video_Game_E_R_Diagram_Design_Project

## Overview  

This project aims to design a relational database schema for a video game platform, specifically for managing clans, players, and performance analysis in a strategic multiplayer game. The platform helps players manage their clans, track their performance, participate in wars, and communicate within the game. The database captures player details, clan information, war assignments, performance statistics, and more.  

## E-R Diagram  

Below is the Entity-Relationship (E-R) diagram for the database schema:  

![E-R Diagram](https://github.com/Sayed-Hossein-Hosseini/Video_Game_E_R_Diagram_Design_Project/blob/master/E_R%20Diagram/Entity%20Relationship%20Diagram.png)  

## Database Entities  

### 1. **User**  
   - **Attributes**: Username, Email Address, IP Address, Password  
   - **Description**: Stores user credentials for authentication and login purposes.  

### 2. **Registration**  
   - **Attributes**: Username, Email Address, IP Address, Password, Role, Full Name, Level, Registration Date, Verification Status  
   - **Description**: Tracks user registration details.  

### 3. **Login**  
   - **Attributes**: Username, Email Address, IP Address, Password, Login Date, Login Status  
   - **Description**: Tracks login attempts, including success or failure.  

### 4. **Player**  
   - **Attributes**: Player ID  
   - **Description**: Represents a unique player in the game.  

### 5. **Deputy**  
   - **Attributes**: Player ID, Coordination Rating, Support Skills  
   - **Description**: Represents a deputy player with special roles and ratings.  

### 6. **Leader**  
   - **Attributes**: Player ID, Strategy Rating, Leadership Skills  
   - **Description**: Represents a leader player with specific leadership skills.  

### 7. **Member**  
   - **Attributes**: Player ID, Contribution Rating, Activity Status  
   - **Description**: Represents a member of a clan with performance ratings.  

### 8. **Player Profile**  
   - **Attributes**: Player ID, Full Name, Avatar, Clan Tag, Num-Star Earned, Num-Successful Attacks, Per-Destruction, Role  
   - **Description**: Stores additional information about players such as their achievements and clan affiliations.  

### 9. **Privacy Setting**  
   - **Attributes**: Player ID, Owner Type, Clan Info, Access Level, Tactics, Status Statistics  
   - **Description**: Tracks privacy settings for players and their access to clan information.  

### 10. **Email**  
   - **Attributes**: Email Address, Verification Status, Verification Date  
   - **Description**: Stores email-related information for user verification.  

### 11. **Performance Analysis**  
   - **Attributes**: Analysis ID, Successful Attacks, Defensive Successful, Stars Earned, Destruction Percentage, Contribution Score  
   - **Description**: Stores performance metrics for each player or clan.  

### 12. **Clan**  
   - **Attributes**: Name, Clan Tag, Level, Num-Members, Rules and Explanations  
   - **Description**: Represents a clan with its details and rules.  

### 13. **Join**  
   - **Attributes**: Join ID, Join Date, Approval Status  
   - **Description**: Represents a player joining a clan.  

### 14. **WAR**  
   - **Attributes**: WAR ID, Start Date, End Date, WAR Status  
   - **Description**: Tracks wars between clans, including start and end dates, and status.  

### 15. **WAR Assignment**  
   - **Attributes**: Assignment ID, Task / Goal, Task / Goal Status  
   - **Description**: Tracks assignments during wars, including the task status.  

### 16. **Notification**  
   - **Attributes**: Notification ID, Type, Message, Created At  
   - **Description**: Stores notifications to players, such as war events or rule changes.  

### 17. **Clan Member Info**  
   - **Attributes**: Clan Member Info ID, Role in Clan, Game Level, Num-Attacks and Defenses, Per-Participation in the WAR  
   - **Description**: Stores additional information about members in a clan related to their participation in wars.  

### 18. **Report**  
   - **Attributes**: Report ID, Generated Date, Report Type, Details  
   - **Description**: Represents generated reports, such as clan performance or war outcomes.  

## Relationships  

- **Authentication**: Links the `User` entity to the `Email` entity for verification.  
- **Belongs To**: Associates the `User` entity with the `Player` entity to identify which player the user belongs to.  
- **Has Profile**: Connects the `Player` entity with the `Player Profile` entity to store detailed information about the player.  
- **Managed By**: Links the `Player` entity with the `Privacy Setting` entity to manage privacy preferences.  
- **Linked To**: Connects the `Player` entity with the `Email` entity for player email tracking.  
- **Analysis**: Links `Player Profile` to `Performance Analysis` for performance tracking.  
- **Creates**: The `Leader` entity creates and manages `Clan` entities.  
- **Has Member**: The `Clan` entity can have multiple `Join` entities, representing players joining the clan.  
- **Based On**: The `Clan` entity can generate `Report` entities based on clan performance or participation.  
- **Assigned To**: Links `Clan Member Info` with `WAR Assignment` for task management in wars.  

## Schema Guide  

### Primary Key:  
- **Attribute**: The unique identifier for each entity, e.g., `Player ID`, `WAR ID`.  

### Foreign Key:  
- **Attributes**: References to primary keys from other entities to create relationships, e.g., `Player ID` in the `Leader` table refers to `Player ID` in the `Player` table.  

## License  

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.  

## Author  

- Sayyed Hossein Hosseini DolatAbadi
