## 1. Summary
Statistical analyses were performed on the continuous and categorical variables against the markup on minimum ticket prices.

### 2. Continuous Variables
#### Variables Analyzed:
  1. Spotify Popularity
  2. Spotify Followers
  3. Quantity of Tickets Listed
  4. Length of Presale (Days)
  5. Number of Days on sale
  6. Days until Show
  7. Artist count per event

#### Tests Used
Because markups followed a logarithmic distribution, both Spearman and Pearson correlations were calculated.
#### Results
##### Scatterplots
![Scatterplots](Graphs/continuous_scatterplots.png?raw=true)
##### Artist Count Summary
![Scatterplots](Graphs/artistcount_summary.png?raw=true)
##### Correlations Table
|        Column        |PearsonR|PearsonR_pvalue|Pearson_NullHypothesis|SpearmanR|SpearmanR_pvalue|Spearman_NullHypothesis|
|----------------------|-------:|--------------:|----------------------|--------:|---------------:|-----------------------|
|avg_ticket_listings   |-0.09455|       0.000000|Reject                | -0.19922|        0.000000|Reject                 |
|spotify_avg_followers | 0.04988|       0.002227|Reject                | -0.09213|        0.000000|Reject                 |
|spotify_avg_popularity| 0.04966|       0.002328|Reject                | -0.09179|        0.000000|Reject                 |
|presale_length        |-0.07767|       0.000002|Reject                | -0.18001|        0.000000|Reject                 |
|days_on_sale          |-0.04559|       0.005186|Reject                | -0.16739|        0.000000|Reject                 |
|days_until_show       |-0.07371|       0.000006|Reject                |  0.01310|        0.422253|Accept                 |
|artist_count          | 0.01077|       0.509459|Accept                |  0.01036|        0.525406|Accept        

Spearman R values are generally higher than their Pearson R counterparts. Artist Count and potentially Days Until Show are not correlated to price markups and may not be relevant features.

### 3. Categorical Variables
#### Variables Analyzed:
  1. Genre
  2. Subgenre
  3. Day of Week
  4. Promoter
  5. Ticket Source

### Tests Used
T tests were used to compare the markups of each feature category to the whole dataset's markup mean. Then an ANOVA f-test was used to determine if the means of categorical features were significantly different. After confirming a statistically significant difference in markup means amongst categories, a Paired Tukey test was used to compare every unique pair of categories.

### Results
The results corroborated the conclusions drawn from the initial graphic data exploration.
#### 3.1 Genre
![Genre Summary](Graphs/genre_summary.png?raw=true)
##### T-Test
The Dance/Electronic, Jazz, Pop, R&B, Religous, Rock, Undefined, and World genres had markups significantly different from the mean.
##### ANOVA/Paired Tukey
Pop & Country, Pop & Rock, Rock & Undefined, Rock & World pairs had significantly different means.
#### 3.2 Subgenre
![Subgenre Summary](Graphs/subgenre_summary.png?raw=true)
##### T-Test
Adult Contemporary, Club Dance, Gospel, Jazz, Latin, Pop, R&B, Undefined, and World subgenres had significantly different markups from the overall mean.
##### ANOVA/Paired Tukey
The Latin & Pop and Pop & Soul pairs had significantly different markups.
#### 3.3 Day of Week
![Day of Week Summary](Graphs/day_summary.png?raw=true)
##### T-Test
Markups for events on Sunday and Monday were significantly below the mean markup.
##### ANOVA/Paired Tukey
No statistically significant difference was found for markups between days of the week.
#### 3.4 Promoter
![Promoter Summary](Graphs/promoter_summary.png?raw=true)
##### T-Test
Most promoter categories have statistically significant differences from the overall mean.
The null hypothesis is rejected for AEG Live, Crossroad Presents, Live Nation, and 'Other' for having markups significantly below the mean, and Masquerade, and 'Promoted by Venue' having markups significantly greater than the mean.
##### ANOVA/Paired Tukey
Events by Masquerade had markups significantly higher than all other promoters
#### 3.5 Ticket Source
![Day of Week Summary](Graphs/source_summary.png?raw=true)
##### T-Test
Events with tickets only on Stubhub have significantly higher markups than those of the dataset. Events with tickets on both Stubhub and SeatGeek have significantly lower markups.
##### ANOVA/Paired Tukey
Differences are statistically significant for tickets on both platforms vs. Stubhub, and SeatGeek vs. Stubhub.
