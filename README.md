# NBA-MVP-Predictions
A multi-process project including Web Scraping, Data Cleaning and Machine Learning to predict the top five NBA MVPs in a year.

Utilizing the site https://www.basketball-reference.com/, this project contains files for Scraping,
Cleaning and Training/Testing the data relevant to the MVPs of the NBA of each year.
Ultimately, using Average Precision Error, Ridge Regression results in approximately 72% accuracy
while RFR has ~74% accuracy.

## Executables

- **NBA Stats Web Scraping.ipynb** utilizes Selenium's Chromedriver and BeautifulSoup to navigate, read and parse information
from various parts of the site. Notable features include Javascript handling, Timeout handling and downloading of resource files to reduce strain on the server.

- **NBA Stats Web Cleaning.ipynb** processes each csv created in the scraping step to homogenize and standardize information.
The resultant Pandas DataFrames are combined into one DF to be used as the source dataset for Machine Learning.

- **NBA Stats Machine Learning.ipynb** performs last touches to clean-up, then uses the Ridge and RFR models to train and test the data.
Error metrics used include MSE and Average Precision Error. Ranking is added to increase weight of player position in the MVP leaderboard.

## Resources

- **abbreviations.csv** contains the mapping between team names and their abbreviations to allowing merging of team data with player data.

## Results
- Effective Field Goal Percentage is the strongest indicator for ranking top five in the MVPs, followed by Defensive Rebounds and then the Win/Loss-Percentage of the team
- Suggests that the team a player played on is correlated with their chance of becoming an MVP. 
-- Better teams are likely to attract higher-performing players, which in turn are more likely to play a winning game
- Each stat contributes to under 10% of the target, suggesting a player is more likely to get MVP status if they excel in several areas rather than specializing in one or two

### Notes
- Features were not scaled prior to testing
- No features were dropped
- Categorical information was not included in Ridge regression

### Credit
Project created by [Dataquest](https://www.dataquest.io/). [Link to part one here.](https://www.youtube.com/watch?v=JGQGd-oa0l4)
