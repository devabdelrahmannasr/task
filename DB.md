## Table: `teams`

| Column Name       | Data Type       | Description                     |
|-------------------|----------------|---------------------------------|
| id (PK)           | int            | Primary Key                     |
| team_name         | string         | Team Name                       |
| team_image        | string         | Team Image (nullable)           |
| age_group         | string         | Age Group                       |
| is_belong_to_club | boolean        | Belongs to Club or Team         |
| club_or_team_name | string         | Name of Club or Team (nullable) |
| status            | boolean        | Team Activation Status          |
| notes             | text           | Notes (nullable)                |

## Table: `team_players`

| Column Name       | Data Type       | Description                     |
|-------------------|----------------|---------------------------------|
| id (PK)           | int            | Primary Key                     |
| team_id (FK)      | int            | Team ID (Foreign Key to Teams)  |
| name              | string         | Player Name                     |
| email             | string         | Player Email                    |
| phone_number      | string (unique)| Phone Number                    |
| age_group         | string         | Age Group                       |
| player_positions  | string         | Player Positions                |
| tshirt_size       | string         | T-shirt Size                    |
| ice_contact_phone | string         | ICE Contact Phone               |
| ice_contact_name  | string         | ICE Contact Name                |
| ice_contact_type  | string         | ICE Contact Type                |
