# Date-and-month-processing-Dataset-created-using-DAX-Power-BI-Desktop

📄 Dataset Description

This dataset was generated in Power BI using DAX to create a complete date table and perform various date and text transformations. It covers the period from January 1, 2024 to January 1, 2025, and includes multiple calculated columns to support time-intelligence analytics and data preprocessing practice.

Key Features Included
🗓️ 1. Date Table Creation

Dataset
CALENDAR(DATE(2024,01,01), DATE(2025,01,01))
Creates a continuous date range for one full year.

🔢 2. Numeric Transformations

MonthNum – Extracts the month number from each date.

WeekNum – Returns the week number of the year.

Weekday – Numeric weekday (1 = Sunday).

📝 3. Text-Based Date Features

Month Name – Full month name (e.g., "January").
FORMAT([Date], "MMMM")

Month Short Name – Abbreviated month (e.g., "Jan").
FORMAT([Date], "MMM")

Day Short Name – 3-letter weekday abbreviation.
FORMAT([Date], "DDD")

🔗 4. Concatenated Columns

Con Month Day Short Name
Combines month short name + day short name.
Example: "JanMon"

Con Month Day Short Name with Delimiter
Inserts a hyphen between the values.
Example: "Jan-Mon"

✂️ 5. String Manipulation (Text Functions)

Left Fun – First 3 characters of the month name.

Right Fun – Last 2 characters of the month name.

Mid Fun – Extracts characters from the middle of the month name.

Length of Characters – Counts total characters in the month name.

__________________________________________________________________

DAX Code With Description:

Dataset = CALENDAR(DATE(2024,01,01), DATE(2025,01,01))   
-- Creates a date table from Jan 1, 2024 to Jan 1, 2025

MonthNum = MONTH('Dataset'[Date].[Date])  
-- Extracts the month number (1–12) from each date

Weekday = WEEKDAY('Dataset'[Date].[Date],1)  
-- Returns numeric weekday (1 = Sunday, 7 = Saturday)

WeekNum = WEEKNUM('Dataset'[Date].[Date],1)  
-- Returns the week number of the year (starting on Sunday)

Month Name = FORMAT('Dataset'[Date].[Date],"MMMM")  
-- Extracts the full month name (e.g., "January")

Month Short Name = FORMAT('Dataset'[Date].[Date],"MMM")  
-- Extracts the 3-letter month abbreviation (e.g., "Jan")

Day Short Name = FORMAT('Dataset'[Date].[Date],"DDD")  
-- Extracts 3-letter day name (e.g., "Mon")

Con Month Day short Name =
    CONCATENATE('Dataset'[Month Short Name],'Dataset'[Day Short Name])  
-- Joins month short name + day short name (e.g., "JanMon")

Con Month Day short Name with Delimiter =
    CONCATENATE(CONCATENATE('Dataset'[Month Short Name],"-"),'Dataset'[Day Short Name])  
-- Joins values with a hyphen (e.g., "Jan-Mon")

Left Fun = LEFT('Dataset'[Month Name],3)  
-- Extracts the first 3 characters of the full month name

Right Fun = RIGHT('Dataset'[Month Name],2)  
-- Extracts the last 2 characters of the month name

Length of characters = LEN('Dataset'[Month Name])  
-- Returns number of characters in the month name

Mid Fun = MID('Dataset'[Month Name],1,2)  
-- Extracts characters starting from position 1, taking 2 characters (substring)
