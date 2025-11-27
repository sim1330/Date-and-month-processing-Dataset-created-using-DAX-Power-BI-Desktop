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
