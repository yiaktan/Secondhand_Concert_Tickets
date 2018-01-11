## 1 Data Gathering
Event data was first gathered from the Ticketmaster API for the whole US. Datetime columns were localized, and duplicates and parking passes were dropped. The same process was repeated for data from Stubhub and SeatGeek. I then used the fuzzywuzzy module to find fuzzy matches of venue names from Ticketmaster to Stubhub and SeatGeek. The three data sets were then joined based on venue name, and date and time. I then iterated through each unique artist and called its popularity and followers values from Spotify. The final dataframe contained about 5000 events from all 50 states, and of all genres of music.

## 2 Dealing with Missing Values
Spotify was missing data for about 200 artists. These missing values were imputed using the median values of the artists subgenre. A separate column was then created recording the number of artist with null values per event.

Several events were also missing ticket sale start dates, and were imputed by calculating the average number of days all events were on sale.
## 3 Feature Engineering
New features created were presale length, number of days on sale, days until show, ticket source, day of the week, min and max markups (Ticketmaster and Stubhub only provide the minimum and maximum ticket prices of each event, so price analysis was done comparing minimums to minimums, and maximums to maximums.), and the average of number of tickets listed per event (Sum of SH and SG listings divided by two, if both had listings).<br><br>
## 4 Outliers
Max ticket prices included a lot of outlying values (Over 1000 events with max resale prices outside of 1.5\*IQR). Rather than drop these values and reduce the sample size, I instead chose to focus the analysis on minimum ticket prices.

## 5 Categories with Few Samples
Categorical features contained categories with only a few samples, making it difficult to generalize those categories. I recategorized genres, subgenres, and promoters with n < 50 sample sizes as "Other", and dropped venue states with  n < 50 events.
Additionally, all events more than 6 months out were dropped, as there were few samples and its prices for those tickets would probably change over time.
