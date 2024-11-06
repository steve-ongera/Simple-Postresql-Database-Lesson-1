# Simple Postresql Database User Management System

## Overview
This is a simple user management system implemented in PostgreSQL. The system maintains a database of users with their basic information including usernames and ages, with support for schema modifications.

## Database Schema

### Users Table Initial Structure
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

### Schema Modifications

#### Adding Columns
```sql
-- Add email column
ALTER TABLE users ADD COLUMN email VARCHAR(255);

-- Add email column with default value
ALTER TABLE users ADD COLUMN email VARCHAR(255) DEFAULT 'example@example.com';
```

#### Removing Columns
```sql
-- Drop email column
ALTER TABLE users DROP COLUMN email;
```

#### Renaming Elements
```sql
-- Rename table
ALTER TABLE users RENAME TO cars;

-- Rename column
ALTER TABLE users RENAME COLUMN username TO student_name;
```

### Data Querying

#### Retrieve Users by Age Range
```sql
SELECT username, age
FROM users
WHERE age >= 10 AND age <= 27;
```

### Data Cleanup Operations

#### Truncate Table
```sql
TRUNCATE TABLE users;
```

#### Drop Table
```sql
DROP TABLE users;
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
- Email (when added): Maximum length of 255 characters

## Getting Started

### Prerequisites
- PostgreSQL database server (version 9.0 or higher)
- Basic knowledge of SQL

### Installation
1. Ensure PostgreSQL is installed and running
2. Connect to your PostgreSQL server
3. Execute the table creation SQL command
4. Run the insert commands to populate initial data

## Common Operations

### Adding Email to Existing Table
```sql
ALTER TABLE users ADD COLUMN email VARCHAR(255) DEFAULT 'example@example.com';
```

### Querying Users Within Age Range
```sql
SELECT username, age
FROM users
WHERE age >= 10 AND age <= 27;
```

### Cleaning Up Database
```sql
-- To remove all data but keep structure
TRUNCATE TABLE users;

-- To completely remove table
DROP TABLE users;
```

### Renaming Database Elements
```sql
-- Rename table
ALTER TABLE users RENAME TO cars;

-- Rename column
ALTER TABLE users RENAME COLUMN username TO student_name;
```

## Important Notes
1. The table structure is flexible and can be modified using ALTER TABLE commands
2. Data can be completely removed using TRUNCATE TABLE
3. The entire table can be dropped using DROP TABLE
4. Column names and table names can be renamed as needed
5. Default values can be specified when adding new columns

## Future Improvements
1. Add primary key constraint to username
2. Include additional user information
3. Add data validation constraints
4. Implement user authentication
5. Add timestamp columns for record tracking
6. Implement foreign key relationships
7. Add indexing for better query performance

## Contributing
Feel free to submit issues and enhancement requests.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Support
For support, please create an issue in the repository or contact the database administrator.

## Version History
- v1.0: Initial table creation with username and age
- v1.1: Added support for email column
- v1.2: Added table and column renaming capabilities
- v1.3: Added data cleanup operations