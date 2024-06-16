# 24 Hour Player Peak Analysis for Games on SteamDB

- Hasti Karimi
- Fateme Mohammadi
- Ali Lotfollahi

## Introduction

With the video game industry growing day by day, penetrating our lives more and more, we decided to work on analyzing them based on the data on Steam DB website targeting their 24 hour player peak. 24 hour player peak, as the feature to be modeled by other criteria, demonstrates what is the maximum number of players playing a certain game concurrently in each day. It is a metric to assess how much involving a game is in a way people would deliberately spend their valuable time playing it. In this project-assignment, we delve into how data was extracted, modified, and employed so that predictive models could form addressing 24 hour player peak.

## Step 1: Data Collection

The first step was gathering a rich set of data from the selected website <http://steamdb.info>. For this purpose, we conducted three scraping scripts held in following files:

- `webScrape_main.ipynb`
- `webScrape_price.ipynb`
- `webScrape_URL.ipynb`

`webScrape_main.ipynb` is where most work is done. It extracts many features from each game's profile on SteamDB website. However, two auxillary scripts were proved to be necessary during the project so that this step could be possible.

First `webScrape_URL.ipynb` extracts all urls associated with each game in Steam DB's search page. It creates a mapping from the name of each game to its corresponding url and stores it in `game_urls.txt`.

![figure 1-1](./fig1-1.png)

Next, `webScrape_main.ipynb` extracts needed data inscribed on each game's profile including:

- NAME
- STORE_GENRE
- RATING_SCORE
- N_SUPPORTED_LANGUAGES
- DEVELOPERS
- SUPPORTED_PLATFORMS
- POSITIVE_REVIEWS
- NEGATIVE_REVIEWS
- TECHNOLOGIES
- RELEASE_DATE
- TOTAL_TWITCH_PEAK
- N_DLC
- 24_HOUR_PEAK

![figure 1-2](./fig1-2.png)

However, this was not the end since price was difficult to be drawn out of this page. Thus, there came the idea of `webScrape_price.ipynb`. This script scrapes prices off of Steam DB's search page. This enabled us to ignore all the complexity of mining price for the correct currency from each game's profile page.

So far, we had accumulated about 3000 entries of games in our tables. Although this number is rather small for such a huge task, we stopped collecting data here due to time deficiencies and the lack of necessary horizontal mining power. Having that said, data was now ready for further transformations.

## Step 2: Preprocessing
