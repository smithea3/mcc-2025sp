---
title: 🏠 Home
short_title: Home
authors:
  - name: Ethan A. Smith
    affiliations:
      - Mitchell Community College
    email: esmith3@mitchellcc.edu
keywords: syllabus, mathematics, MitchellCC
---

# 🏠 Home

## MAT 171-OSI1

## MAT 171-OSI2

## MAT 273-SST1 & MST1

## MAT 280-SST1 & MST1

## Helpful Code
The following code allows the user to generate a list of dates from the start date to the end date and do so using specific days of the week.
:::{note}
This code was used to generate the course schedules on this site.
:::
```python
from datetime import datetime, timedelta

def generate_dates(start_date, end_date, weekdays):
    """
    Generate a list of dates between start_date and end_date that match the given weekdays.
    
    :param start_date: The start date as a datetime object.
    :param end_date: The end date as a datetime object.
    :param weekdays: A list of desired weekdays (e.g., ['Monday', 'Wednesday']).
    :return: A list of formatted date strings.
    """
    # Create an empty list to hold the formatted dates
    date_list = []

    # Convert weekdays to lowercase for comparison
    weekdays = [day.lower() for day in weekdays]

    # Iterate over each date in the range
    current_date = start_date
    while current_date <= end_date:
        # Check if the current date's weekday is in the list of desired weekdays
        if current_date.strftime('%A').lower() in weekdays:
            # Format the date as "weekday, month day"
            formatted_date = current_date.strftime('%A, %B %d')
            date_list.append(formatted_date)
        # Move to the next day
        current_date += timedelta(days=1)

    return date_list

# Define the start and end dates
start_date = datetime(2024, 8, 19)
end_date = datetime(2024, 12, 16)

# Define the desired weekdays
desired_weekdays = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']

# Generate the list of dates
formatted_dates = generate_dates(start_date, end_date, desired_weekdays)

# Print the list of dates
for date in formatted_dates:
    print('**'+date+'**'+'\n')
```