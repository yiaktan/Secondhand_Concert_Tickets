# 1. Dealing with missing values
Spotify was missing data for about 200 artists. These missing values were filled using the median values of the artists genres. A seperate column was then created recording the number of artist with null values per event.

# 2. Outliers
Max ticket prices included a lot of outlying values (Over 1000 events with max resale prices outside of 1.5\*IQR Rather than drop these values and reduce the sample size, I instead chose to focus the analysis on ticket minimum prices.
