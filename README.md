# Simple Postresql Database Lesson 1

## Overview
This is a simple user management system implemented in PostgreSQL. The system maintains a database of users with their basic information including usernames and ages.

## Database Schema

### Users Table
The system uses a single table with the following structure:

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| username | VARCHAR(200) | User's unique identifier |
| age | INTEGER | User's age in years |

## SQL Operations

### Table Creation
```sql
CREATE TABLE users(
    username VARCHAR(200),
    age INTEGER
);
```

### Data Manipulation

#### Adding Single User
```sql
INSERT INTO users (username, age)
VALUES ('wangechi', 31);
```

#### Adding Multiple Users
```sql
INSERT INTO users (username, age)
VALUES 
    ('omko', 25),
    ('benson', 30),
    ('hassan', 28),
    ('muthoni', 35);
```

#### Updating User Information
```sql
UPDATE users
    SET age = 20
    WHERE username='gadafi';
```

#### Retrieving User Data
```sql
SELECT * 
FROM users;
```

## Sample Data
The system comes pre-populated with the following sample users:
- wangechi (31 years)
- omko (25 years)
- benson (30 years)
- hassan (28 years)
- muthoni (35 years)

## Technical Specifications

### Data Constraints
- Username: Maximum length of 200 characters
- Age: Integer values only

## Getting Started

### Prerequisites
- PostgreSQL database server (version 9.0 or higher)
- Basic knowledge of SQL

### Installation
1. Ensure PostgreSQL is installed and running
2. Connect to your PostgreSQL server
3. Execute the table creation SQL command
4. Run the insert commands to populate initial data

## Usage Examples

### Adding a New User
```sql
INSERT INTO users (username, age)
VALUES ('new_user', 25);
```

### Updating User Age
```sql
UPDATE users
SET age = 26
WHERE username = 'new_user';
```

### Retrieving All Users
```sql
SELECT * FROM users;
```

## Contributing
Feel free to submit issues and enhancement requests.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Future Improvements
1. Add primary key constraint to username
2. Include additional user information (email, full name, etc.)
3. Add data validation constraints
4. Implement user authentication
5. Add timestamp columns for record tracking

## Support
For support, please create an issue in the repository or contact the database administrator.