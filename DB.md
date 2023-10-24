## Table: `sports_tournaments`

| Column Name           | Data Type       | Description                         |
|-----------------------|----------------|-------------------------------------|
| id (PK)               | int            | Primary Key                         |
| tournament_name       | string         | Tournament Name                     |
| description           | text           | Tournament Description              |
| capacity              | int            | Tournament Capacity                 |
| start_date            | date           | Tournament Start Date                |
| end_date              | date           | Tournament End Date                  |
| image                 | string         | Tournament Image (nullable)         |
| terms_page_content    | long text      | Terms and Conditions Content         |
| price_per_team        | decimal(10, 2) | Price per Team (in decimal format)   |
| team_members_capacity | int            | Team Members Capacity                |

## Table: `teams`

| Column Name          | Data Type       | Description                     |
|----------------------|----------------|---------------------------------|
| id (PK)              | char(36)       | Primary Key                     |
| team_name            | string         | Team Name                       |
| team_image           | string         | Team Image (nullable)           |
| age_group_id(FK)     | char(36)        |Foreign Key to age_group_definitions|
| belongs_to_club      | boolean        | Belongs to Club or Team         |
| club_or_team_name    | string         | Name of Club or Team (nullable) |
| team_status          | enum('actvie','inactive','pending')        | Team Activation Status          |
| payment_status       | boolean        | Team Payment Status             |
| payment_ref_id       | string         | External Ref ID                 |
| team_notes           | text           | Notes (nullable)                |
| sports_tournament_id  | char(36)      | Foreign Key to sports_tournaments|

## Table: `team_players`

| Column Name          | Data Type       | Description                     |
|----------------------|----------------|---------------------------------|
| id (PK)              | char(36)       | Primary Key                     |
| team_id (FK)         | char(36)       | Team ID (Foreign Key to Teams)  |
| player_name          | string         | Player Name                     |
| player_email         | string         | Player Email                    |
| phone_number         | string (unique)| Phone Number                    |
| player_age           | int            | Age                             |
| tshirt_size          | enum           | T-shirt Size                    |
| emergency_contact_phone    | string         | Emergency Contact Phone               |
| emergency_contact_name     | string         | Emergency Contact Name                |
| emergency_contact_type     | string         | Emergency Contact Type                |


## Table: `tournament_faqs`

| Column Name        | Data Type       | Description                           |
|--------------------|----------------|---------------------------------------|
| id (PK)            | char(36)       | Primary Key                           |
| question           | text           | FAQ Question                          |
| answer             | long text      | FAQ Answer                            |
| sports_tournament_id | char(36)     | Foreign Key to related sports tournament |

## Table: `age_group_definitions`

| Column Name       | Data Type | Description                   |
|-------------------|-----------|-------------------------------|
| id (PK)           | char(36)       | Primary Key                   |
| age_group_range   | string    | Age Group Range               |
| sports_tournament_id | char(36)   | Foreign Key to related sports tournament |


