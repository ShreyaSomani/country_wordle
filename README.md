
# 1. Description

A geography guessing game with the following rules:

- You are given the outline of a mystery Country or Territory 🌏
- If you guess the correct Country then you win 🥳
- If you guess incorrectly 6 times then you lose 😔
- Each incorrect guess will reveal information that might help you locate the mystery Country:
    - 📏 The `distance` that the center of the guess Country is away from the mystery Country
    - 🧭 The `direction` that points from the guess Country to the mystery Country (on a 2D map)
    - 🥈 The `proximity` percentage of how correct the guess was. A guess on the opposite side of the globe will be `0%` and the correct guess will be `100%`.

### Data Sources and Caveats

- World Bank: [World Boundaries GeoDatabase](https://datacatalog.worldbank.org/search/dataset/0038272/World-Bank-Official-Boundaries)
    - Provides Country and Territory shapes, locations, and names
    - Loaded into SQLite + Spatialite database (see original location guessing [repository on github](https://github.com/gerardrbentley/streamlit-location-guesser))
    - Some boundaries may not be precise or might include satellite territories in addition to mainland
- 📏 `distance` is the [Haversine Distance](https://en.wikipedia.org/wiki/Haversine_formula) calculated based on the [centroids](http://wiki.gis.com/wiki/index.php/Centroid) of the Countries calculated using GeoPandas
    - Countries that share a border will **NOT** have 0 km `distance`
    - The maximum `distance` possible is roughly `20000 km` (two points on opposite sides of the globe)
    - The `proximity` percentage is based on the maximum `distance`


# 2. Live Link 
https://shreyasomani-country-wordle-streamlit-app-85iw28.streamlit.app/

# 3. Screenshots
![Country Wrodle1](https://user-images.githubusercontent.com/57498575/208485816-4ca00c78-f87e-4cf9-b1cc-0febc42f9064.png)
![Country Wrodle2](https://user-images.githubusercontent.com/57498575/208485836-37d5528f-4ee5-451f-ae3f-e526dda06f7f.png)
![Country Wrodle3](https://user-images.githubusercontent.com/57498575/208485856-061aedb5-5360-4d67-924a-a2f1a3175bf9.png)
![Country Wrodle4](https://user-images.githubusercontent.com/57498575/208485864-c2f8b37e-1f68-461b-9318-0b44a481ee12.png)
