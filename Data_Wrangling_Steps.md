## 1.1 Data Gathering
Event data was first gathered from the Ticketmaster API for the whole US. Datetime columns were localized, and duplicates and parking passes were dropped. The same process was repeated for data from Stubhub and SeatGeek. I then used the fuzzywuzzy module to find fuzzy matches of venue names from Ticketmaster to Stubhub and SeatGeek. The three data sets were then joined based on venue name, and date and time. I then iterated through each unique artist and called its popularity and followers values from Spotify. The final dataframe contained about 5000 events from all 50 states, and of all genres of music.

## 1.2 Dealing with missing values
All events with missing ticket prices were dropped, as these are the key features to the dataset and should not be distorted using rough estimates.

Spotify was missing data for about 200 artists. These missing values were filled using the median values of the artists genres. A seperate column was then created recording the number of artist with null values per event.

## 1.3 Outliers
Max ticket prices included a lot of outlying values (Over 1000 events with max resale prices outside of 1.5\*IQR. Rather than drop these values and reduce the sample size, I instead chose to focus the analysis on minimum ticket prices.
