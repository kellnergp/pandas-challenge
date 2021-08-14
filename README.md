# pandas-challenge
Bootcamp pandas homework

## Import Dependencies and read in Data

First, import the pandas library.
Next, use pd.read_csv to import the source data into a dataframe.

## Player Count

Call the 'SN' column from the dataframe and drop duplicates to find all unique players.
The player count is equal to the length of the unique player list object.

For presentation, create a dataframe with the column 'Total Players' and the value returned by the len() function.

Display the dataframe.

## Purchasing Analysis (Total)

To determine the number of unique items, call the 'Item Name' column and drop duplicates.
Then, create a variable with the .count() of the unique items.

Mean purchase price, number of purchases, and total revenue can be determined by applying pandas' native analysis functions to the 'Price' column of the source dataframe.
Respectively, they are determined with mean(), count(), and sum() functions.

All 4 values are placed into a new dataframe with column names denoting their meaning.
Formatting for the dollar values are cleaned up by assigning the currency format to the column maps.

Finally, the cleaned dataframe is displayed.

## Gender Demographics

First, the 'SN' and 'Gender' columns are called into a new dataframe.
Duplicates are removed by applying the drop_duplicates() function to the 'SN' subset.

Gender totals are found by applying count() to a groupby object sorted by Gender.
Percentages of total players are found by dividing the gender count column by the playercount value from the second step and multiplying by 100.

Formatting is cleaned by setting the percentage format to the proper column map, renaming the 'Total Count' column, and removing the header from the 'Gender' column.

The resulting dataframe is displayed.

## Purchasing Analysis (Gender)

Call the 'Gender' and 'Price' columns to a new dataframe for sake of simplicity.

As in the earlier step, purchase count, mean purchase price, and total purchase value are determined through the use of native analysis functions.
Create one groupby object on 'Gender' for each measure, count(), mean(), and sum() respectively.

Next, merge all three groupby objects on 'Gender' and rename the columns to fit.
Then, rename columns to match what they are measuring.

Average total purchase per person is calculated by dividing the total purchase value column by the total count column from the Gender Demographics results dataframe in the previous step.

Clean formatting by repeating the currency formatting step from the earlier purchasing analysis step.

## Age Demographics

Call the 'SN' and 'Age' columns from the source dataframe.
Reduce to unique users with drop_duplicates() on 'SN'.

Use the max() function to find the oldest user for use as the final bin edge.

Create bins and bin labels for under age 10, over age 40, and 5 year increments in between.
Use pd.cut() to bin unique users by age group and place the results into a new dataframe, ensuring that it is sorted by ascending age.

Rename the column to 'Total Count'.

Create a column for percentage of players in each age group by dividing the total count column by the playercount from the second step and mutiplying by one hundred.

Adjust formatting for the percentage column as was done in the Gender Demographics step.

## Purchasing Analysis (Age)

Call 'Age' and 'Price' from the source dataframe.

Generate a list of the age range for each purchase by applying the bins from the previous step to the 'Age' column. 
Create a new dataframe with this list of age ranges and the 'Price' column from the previous dataframe.

Create a dataframe with the age range purchase counts, average purchase price, total purchase value, and average total purchase per person by repeating the groupby, merge, division, and formatting steps from the Gender purchasing analysis, with appropriate references to the Age Demographics and data.

Display the summary dataframe for this step.

## Top Spenders

Call the 'SN' and 'Price' columns from the source dataframe.

Repeat the analysis steps from previous purchasing analysis steps to determine the purchase count, average purchase price, and total purchase value for each user.

Rename the columns appropriately and sort the dataframe by total purchase value, descending, with the sort_values() pandas function.

Apply the currency formatting as in previous steps and display the summary dataframe.

## Most Popular Items

Call the 'Item ID', 'Item Name', and 'Price' columns from the source dataframe.

Group the data by 'Item ID' and 'Item Name' and find purchase count, average purchase price, and total purchase value with analysis functions as was done in previous purchase analysis steps.

Merge the resulting dataframes and rename the columns to match the provided rubric, as done previously.

Sort this dataframe by purchase count descending with sort_values() and store it in a new dataframe to save time in the next step.

Apply currency formatting once again and display the top 5 rows of the dataframe with the head() function.

## Most Profitable Items

Sort the item purchasing analysis dataframe from the previous step by descending total purchase value to show which items generated the most revenue.

Apply currency formatting as done previously and display the top 5 results with head().
