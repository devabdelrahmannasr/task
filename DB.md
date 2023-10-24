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
| age_group            | string         | Age Group                       |
| belongs_to_club      | boolean        | Belongs to Club or Team         |
| club_or_team_name    | string         | Name of Club or Team (nullable) |
| team_status          | boolean        | Team Activation Status          |
| team_notes           | text           | Notes (nullable)                |
| sports_tournament_id  | int            | Foreign Key to sports_tournaments|

## Table: `team_players`

| Column Name          | Data Type       | Description                     |
|----------------------|----------------|---------------------------------|
| id (PK)              | char(36)       | Primary Key                     |
| team_id (FK)         | int            | Team ID (Foreign Key to Teams)  |
| player_name          | string         | Player Name                     |
| player_email         | string         | Player Email                    |
| phone_number         | string (unique)| Phone Number                    |
| player_age_group     | string         | Age Group                       |
| player_positions     | string         | Player Positions                |
| tshirt_size          | string         | T-shirt Size                    |
| ice_contact_phone    | string         | ICE Contact Phone               |
| ice_contact_name     | string         | ICE Contact Name                |
| ice_contact_type     | string         | ICE Contact Type                |


## Table: `tournament_faqs`

| Column Name        | Data Type       | Description                           |
|--------------------|----------------|---------------------------------------|
| id (PK)            | char(36)       | Primary Key                           |
| question           | text           | FAQ Question                          |
| answer             | long text      | FAQ Answer                            |
| sports_tournament_id | int          | Foreign Key to related sports tournament |
