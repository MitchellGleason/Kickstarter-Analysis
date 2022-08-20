# Kickstarter Analysis
## Overview of Project
The purpose of this project is to visualize Kickstarter campaign (specifically theatre plays) outcomes based on the launch date and funding goal of the campaign. This information will help in the understanding of how one's own campaign compares in relation to others of the same type and to learn trends in order to increase success for future campaigns.
## Analysis and Challenges
The first analysis consists of a comparison between the total number of successful, failed and canceled campaigns and the date on which those campaigns were launched, culminating in the line chart shown here:

![Theatre_Outcomes_vs_Launch](https://user-images.githubusercontent.com/111290810/185723402-d92bd13c-8e7d-4888-b43c-d80f764f270e.PNG)

This is completed in Excel by creating a PivotTable with the provided data. The data selected for the PivotTable fields are as follows:
- Filters
  - Parent Category
  - Years
- Columns
  - Outcomes
- Rows
  - Date Created Conversion
- Values
  - Count of Outcomes

While I did not encounter any challenges with this analysis, this could certainly occur by entering the wrong PivotTable fields or by not removing the 'Years' and 'Quarters' fields when using the 'Date Created Conversion' field.

The second analysis, similar to the first, compares the total number of successful, failed and canceled campaigns and the funding goal that they set. This was done by first setting eleven value ranges of goals, from less than $1000 to greater than $50,000. Next, the total number of successful, failed and canceled campaigns had to be extrapolated from the given data and sorted into each of the eleven goal categories. This was done by using the COUNTIFS() formula in Excel, which with the given data functions as follows: 

*=COUNTIFS(Kickstarter!$D:$D, ">=5000", Kickstarter!$D:$D, "<=9999", Kickstarter!$F:$F, "=successful", Kickstarter!$R:$R, "=plays")*

with variations for the goal and outcome categories. The total number of campaigns per goal category was also calculated by using the SUM() function, which with the given data functions as follows:

*=SUM(B2, C2, D2)*

And finally the percentage of successful, failed and canceled campaigns was calculated by simply dividing the number of successful, failed and canceled campaigns by the respective total number of campaigns per goal category. A line chart was then created to help visualize the percentage of successful, failed and canceled campaigns when compared to the goal categories, shown here:

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/111290810/185723574-16cb42c6-8827-4781-ba0d-1b8ef43eff87.PNG)

The only challenge that was encountered during this was numerous syntax errors while attempting to get the correct syntax for the COUNTIFS() formula with numerous variables within it. This was overcome by referencing the [Microsoft support website](https://support.microsoft.com/en-us/office/countifs-function-dda3dc6e-f74e-4aee-88bc-aa8c2a866842).

## Results
The comparison between successful campaigns and their launch date immediately draws two conclusions. The first visually obvious conclusion is that campaigns that were launched in the month of May had a considerably higher chance of success compared to any other month. While both June and July launch dates have a higher chance of success than the rest of the year, the month of May can certainly be seen as the best time of year to launch a Kickstarer for a theatre play. Secondly, and conversely, launching a campaign in the month of December has a considerably lower chance of success than any other time of the year. This month sees only about a %50 chance of success.

Comparing success rates to their respective goal amount provides an overall less extreme conclusion with three exceptions. While the difference in percentage of successful/failed campaigns between the goal ranges of $5000 to $25000 is negligible, at roughly %50, the extreme ends of the goal ranges provide a different conclusion. First, any theatre play campaign with a goal less than $5000 has a much greater chance at success, with ~%75 with goals under $1000 succeeding and ~%72 with goals between $1000 and $5000 succeeding. Additionally, both of these goal categories have the largest amount of campaigns data points and therefore provide a very good reference to base a decision on. Secondly, goal ranges between $35,000 and $45,000 provide somewhat of an anomaly compared to ranges surrounding them. While the immediate ranges above and below the $35,000 to $45,000 range have a much higher percentage of failed campaigns, this specific range in fact has a high percentage of successful campaigns, at ~%66. However, it is important to note that the $35,000 to $45,000 range has extremely few data references, at only nine total. Third, and conversely, the highest of the goal ranges, from $45,000 and above, provide the highest percentage of failed campaigns. While the number of data sets for this range is not nearly as high as most other ranges, at only seventeen, it is more than the previous conclusion and may be used to some degree of confidence.

The limitations of this dataset include the vast difference in the number of campaigns with goals set below $10,000 and the number with goals set above $10,000. With so few campaigns above $10,000 it may be difficult to confidently rely on that data. Additionally the data used here is not sorted by country, which may have a great effect on the conclusions drawn. The biggest limitation of this dataset, however, is the subjectivity of the premise for a theatre campaign play. While  the data shows that a campaign of $2000 started in May will have a very high chance of success, a bad or unpopular pitch for the play will drastically reduce these numbers.

Other possible tables/graphs that can help visualize this data would be a box plot to see a comparison between set goals and the pledged amount towards those goals. Another great dataset to have would be an average of the numbers of backers per campaign and their average donation which could be used to set an obtainable goal and could be compared to visualize a difference in pledge amounts between smaller and larger set goals.
