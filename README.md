# Loadshedding Schedule Web Application

## Overview
This PHP web application allows users to view loadshedding schedules based on the selected stage and area. The app connects to a database, retrieves relevant schedule data, and displays the results on a web page.

## Features
- Dropdown menus for selecting loadshedding stage and area
- Fetches data from a MySQL database
- Displays loadshedding information, including area name, time, stage, and day

## Files
- **DBConnect.php**: Establishes the connection to the MySQL database.
- **index.php**: Main file containing the form and logic for retrieving and displaying schedule data.

## How It Works
1. **User Input**:
   - Users select a stage (1 to 4) and an area (St Georges, North End, Summerstrand) from dropdown menus.
   - A submit button sends the selections via POST to the same page.

2. **Database Query**:
   - The `$_POST` data is used to construct a SQL query.
   - The query joins three tables (`stage`, `tblLocation`, `schedule`) based on `AreaID` and `StageID`.
   - Results include area name, loadshedding time, stage name, and day.

3. **Displaying Results**:
   - If matching records are found, they’re displayed in a readable format.
   - If no records match, a “0 results” message is shown.

## Prerequisites
- PHP 7.4 or later
- MySQL Database with tables: `stage`, `tblLocation`, `schedule`

## Usage
1. Ensure the database connection in `DBConnect.php` is configured correctly.
2. Access `index.php` via a local or hosted server.
3. Select a stage and area, then click the submit button.
4. View the displayed loadshedding schedule.

## Example Output
```
Area Name: Summerstrand - Times loadshedding 14:00 - Loadshedding stage: Stage 2 - Loadshedding Day: Monday
```

## Potential Improvements
- Validate user input to prevent SQL injection.
- Use prepared statements instead of direct SQL queries.
- Improve the UI with CSS.
- Add error handling for database connectivity issues.

