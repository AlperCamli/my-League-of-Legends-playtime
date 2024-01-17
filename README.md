# my-League-of-Legends-playtime
This is a python code to get the League of Legends match data from Riot api and visualization in some aspects. 

# League of Legends Playtime Analysis

This project analyzes the playtime data of a League of Legends player over a specified period. It retrieves match data using Riot Games API and presents insights into the player's performance and playtime distribution.

## Prerequisites

Before running the code, ensure you have the following:

- Python installed (version 3.x recommended)
- Required Python libraries: `requests`, `pandas`, `matplotlib`

Install the required libraries using:

```bash
pip install requests pandas matplotlib
```
## Getting Started

Clone the repository:
bash
Copy code
git clone https://github.com/your-username/league-of-legends-analysis.git
cd league-of-legends-analysis

Replace RGAPI-32939235-e54a-4149-a664-156bc7a3a0fe with your Riot Games API key in the code.

To get an API key from Riot you can visit the website https://developer.riotgames.com/

Run the main script:

After you replaced the API key with your own, the first code block of the Python notebook will ask for a user name as input, and it will get the last 1000 matches of the account and create a csv file which contains the start date of the match, end date of the match, and the lenght of the match (minutes).


1. Fetching Recent Matches and Creating Dataset:

    - Imports necessary libraries and initializes the Riot Games API key.
    
    - Generates the API URL for fetching summoner data based on the provided player ID.
    
    - Extracts the player's PUUID from the summoner data obtained using the API.
    
    - Handles API requests, including rate-limiting by waiting if the rate limit is exceeded.
    
    - Retrieves recent matches for a given player's PUUID in batches to overcome API limits.
    
    - Takes user input for the player ID, fetches summoner data, and then fetches recent matches for the player.
    
    - If there are matches, iterates through them, extracts relevant information, and populates lists for creating a DataFrame.
    
    - Creates a pandas DataFrame from the lists, saves it to a CSV file, and displays the DataFrame.

2. Filling Missing Dates in Dataset:

    - Loads the CSV file, converts the 'DateOfGame' column to datetime format.
      
    - Creates a DataFrame with all dates in the desired range.
      
    - Merges existing and new DataFrames to fill missing dates and replaces NaN values with 0 for playtime.

3. Calculating Daily Playtime:

    - Groups the merged DataFrame by date and calculates total playtime for each day.
      
    - Converts playtime to hours and rounds to 2 digits.
      
    - Iterates through the DataFrame, printing each row with a formatted date.

4. Weekly Playtime Distribution:

    - Calculates playtime per day, orders days of the week, and plots the average playtime per day.

5. Monthly Playtime Distribution in 2023:

    - Calculates playtime per month, orders months of the year, and visualize the average playtime per month in hours.

6. Weekly Playtime Distribution in 2023:

    - Calculates playtime per week, and visualize the average playtime per week of the year 2023.
      
    - Return the most 5 and the least 10 weeks in timeDuration.
      
7. Finding Top and Bottom Playtime Days:
   
   - Identifies the top 5 weeks with the most playtime and the bottom 10 weeks with the least playtime.
     
   - Prints and displays the results for analysis.

     
## Project Structure

analyze_playtime.py: Main script for fetching and analyzing playtime data.
league_of_legends_dataset.csv: CSV file containing my playtime data.
README.md: Project documentation.

