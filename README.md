# Election_Analysis

## Initial Project Overview
A Colorado Board of Elections employee has given you the following tasks to complete the election audit of a recent congressional election. 

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who received vote.
3. Calculated the total number of votes each candidate won.
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on the popular vote.

## Resources
- Data Source: elections_results.csv
- Software: Python v2021.9.1218897484, Visual Studio Code, 1.60

## Initial Summary
The analysis of the election show that:
- There were 369,711 votes cast in the election.
- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
The candidate results were:
  - Charles Casper Stockham: 23.0% (85,213)
  - Diana DeGette: 73.8% (272,892)
  - Raymon Anthony Doane: 3.1% (11,606)
The winner of the election was:
- Diana DeGette with 272,892, 73.8% of the total 369,911

## Election Audit Overview (Change in Scope)
The election commission has requested additional information:
  - Voter turnout for each county
  - The percentage of votes from each county out of the total count
  - The county with the highest count

Began by adding a county_names list that will be used to hold the names of the counties.  And a county_votes dictionary that will be used to to hold the names of the county as the key and the votes for each county as the values: 

county_names = []
county_votes = {}

Added in a variable to hold the county name of the largest voter turnout and an additional variable to hold the vote count of that county:

lc_turnout = ""
lc_voter = 0

Created a step while reading in the csv file to extract the county name for each row.  If that name is not in the county_list, then append it to the list while adding it to the county_votes dictionary and increasing that counties votes by 1:

    for row in reader:
        total_votes = total_votes + 1
        candidate_name = row[2]

        county_name = row[1]
        if county_name not in county_names:
            county_names.append(county_name)

            county_votes[county_name] = 0

        county_votes[county_name] += 1

Next created a loop structure to retrieve the county and the county votes from the county_votes dictionary and to calculate the percentage of votes for that county while also determining if the county had the most votes, then printing those results to the terminal: 

    for county in county_votes:
        county_vote = county_votes[county]
        county_percent = int(county_vote) / int(total_votes) * 100

        county_results = (f"{county}: {county_percent:.1f}% ({county_vote:,})")
        print(county_results)
        txt_file.write(county_results)

        if (county_vote > lc_voter):
            lc_voter = county_vote
            lc_turnout = county

    largest_county_turnout = (
    f"-------------------------\n"
    f"Largest County Turnout {lc_turnout}\n"
    f"-------------------------\n"
    )
    print(largest_county_turnout)

Last gave the script the ability to write those results to a text file that could be shared with the commision. 

    txt_file.write(largest_county_turnout)

## Election Audit Results
![Results](https://github.com/john10roberts/Election_Analysis/blob/main/Resources/AllResults.png)

The analysis of the election show that:
- There were 369,711 votes cast in the election.
- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
The candidate results were:
  - Charles Casper Stockham: 23.0% (85,213)
  - Diana DeGette: 73.8% (272,892)
  - Raymon Anthony Doane: 3.1% (11,606)
The winner of the election was:
- Diana DeGette with 272,892, 73.8% of the total 369,911

Additional Information requested by Election Committee:

![Additional Results](https://github.com/john10roberts/Election_Analysis/blob/main/Resources/CountyResults.png)
  - Voter turnout for each county
    - Jefferson: 38,855
    - Denver: 306,055
    - Arapahoe: 24,801
  - The percentage of votes from each county out of the total count
    - Jefferson: 10.5%
    - Denver: 82.8%
    - Arapahoe: 6.7%
  - The county with the highest count
    - Denver 

## Election Audit Summary

The script we have created could be used to evaluate elections from the local levels i.e., specific districts, to national elections based on the state outcome.  To accomplish these additional lists and data_dictionaries would need to be created to keep accurate counts of the districts/states involved in the analysis.  For each list/dictionary added you would need to add an addtional if statement in the loop structure that reads in the csv files to account for each district/state to be tracked. You would also need to create another loop that would loop through each new dictionary created for the district/state that you needed.  Lastly, then update the print statements to ensure that all the new districts/states were added.  Ex: 

district_names = []
district_votes = {}

ld_turnout = ""
ld_voter = 0

    for row in reader:
        total_votes = total_votes + 1
        candidate_name = row[2]

        district_name = row[x]
        if district_name not in district_names:
            district_names.append(district_name)

            district_votes[district_name] = 0

        district_votes[district_name] += 1

    for district in district_votes:
        district_vote = district_votes[district]
        district_percent = int(district_vote) / int(district_votes) * 100

        county_results = (f"{district}: {district_percent:.1f}% ({district_vote:,})")
        print(district_results)
        txt_file.write(district_results)

        if (district_vote > ld_voter):
            ld_voter = district_vote
            ld_turnout = district

    largest_district_turnout = (
    f"-------------------------\n"
    f"Largest District Turnout {ld_turnout}\n"
    f"-------------------------\n"
    )
    print(largest_district_turnout)

