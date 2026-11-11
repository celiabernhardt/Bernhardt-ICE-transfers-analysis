
# Analysis of Deportation Data Project ICE detention stints data set 

## Data

This analysis uses the stints dataset from the Deportation Data Project, downloadable here https://deportationdata.org/data/processed/ice.html 
each row is one person's "stint" in a detention center. a person's "stay" often consists of multiple "stints"
across different detention centers.

The data contains, among others, the following columns relevant to the analysis:

- `unique_identifier` — an anonymized string for every person in the dataset which can be used to link them
  across multiple stints/rows
- `book_in_date_time` and `book_out_date_time` — the timestamp that each individual stint began and ended respectively
- `stay_book_in_date_time` and `stay_book_out_date_time`- timestamps for beginning and ending of a person's entire
  stay in detention.

## Methodology

##### Part 1: clean

- filter out rows with no unique_identifier (untrackable)
- filter out unique_identifiers whose first state is null 
- filter out unique_identifiers with multiple stays 
- add columns for:
    - circuit (built-in federal_court_circuit has too many nulls)
    - circuit and state of first detention for each person
    - Voluntary departure (true/false)
      
##### Part 2: analyze

- how many are still in detention?
- of them, how many are in fifth circuit?
- of them, how many have cases never ruled on by a judge?
- how quickly were people transferred into fifth circuit?


## Licensing

All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). The data file in the output/ directory is available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. All files in the data/ directory are released into the public domain.
