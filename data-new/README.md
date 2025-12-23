# Data Documentation

## Source
- Public Divvy bike-share datasets (2019 Q1 and 2020 Q1)
- Raw data files are not included due to size limitations.
  They can be downloaded from the public Divvy trip data source.
- The data has been made available by Motivate International Inc.

## Schema
The datasets consist of anonymized trip-level records, including:
- ride start and end timestamps
- ride duration
- user type (casual or member)
- station information
- **No personally identifiable information is included**

## Preprocessing in Google Sheets
Before importing into SQL for further cleaning, the following minimal preprocessing was performed in Google Sheets:

- Trimmed whitespace from `start_time` and `end_time` columns
- Converted timestamp strings (start_time, end_time) to numeric datetime values
- Created `start_time_number` and `end_time_number` columns
- Calculated `ride_length` as the difference between start and end times
- Added a `day_of_week` column for each ride based on `start_time_number` (using =WEEKDAY formula)
- Exported cleaned tables as CSV files for SQL processing
