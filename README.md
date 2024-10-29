# Analysis of Anime Dataset

In this analysis, I explored an anime dataset using Python.
The analysis included data cleaning, exploratory data analysis (EDA), and visualizations to uncover insights about anime shows.

## Libraries Imported
```python
import pandas as pd
import numpy as np
import plotly.express as px
```

## Dataset Overview
I loaded the dataset using Pandas:
```python
df = pd.read_csv("anime.csv")
```

### Exploratory Data Analysis (EDA)

1. **Data Inspection**
   - Displayed the first and last few entries of the dataset.
   - Checked the shape and structure of the DataFrame, which contains 1000 entries and 22 columns.
   - Obtained a summary of the dataset with descriptive statistics.

2. **Null Values Handling**
   - Identified columns with missing values, including `Synonyms`, `Japanese`, `English`, `Premiered`, `Broadcast`, `Genres`, and `Demographic`.
   - Handled null values by filling them with appropriate alternatives, such as using descriptions and synonyms for `Japanese` and `English`.

3. **Date Parsing**
   - Split the `Aired` column into start and end dates.
   - Parsed the dates and created a new column for the season based on the start month.

4. **Duplicate Entries**
   - Checked for and confirmed that there were no duplicate entries in the dataset.

## Data Visualizations

1. **Top 10 Anime by Popularity**
   - Created a bar chart to visualize the top 10 anime based on popularity scores.
   ```python
   fig = px.bar(Top10_anime_popu, x='English', y='Popularity', title='Top 10 Anime by Popularity')
   fig.show()
   ```

2. **Score Distribution**
   - Generated a histogram to analyze the distribution of scores among the anime.
   ```python
   fig = px.histogram(df, x='Score', nbins=12, title='Score Distribution')
   fig.show()
   ```

3. **Top 7 Years by Total Shows**
   - Produced a bar chart to highlight the top 7 years with the highest number of anime shows released.
   ```python
   fig = px.bar(top_7_years_df, x='Year', y='Total Shows', title='Top 7 Years by Total Shows')
   fig.show()
   ```

4. **Distribution of Anime Types**
   - Created a pie chart to show the distribution of the top 3 types of anime by the number of shows.
   ```python
   fig = px.pie(top_3_tpyes_df, names='Type', values='Total Shows', title='Distribution of the top 3 Types by num of Shows')
   fig.show()
   ```

5. **Top 5 Genres by Total Shows**
   - Generated a bar chart to display the top 5 genres based on the total number of shows.
   ```python
   fig = px.bar(top_5_Geners_df, x='Geners', y='Total Shows', title='Top 5 Genres by Total Shows')
   fig.show()
   ```

6. **Top 10 Studios**
   - Visualized the top 10 studios by the number of shows produced with a bar chart.
   ```python
   fig = px.bar(top_10_studios_df, x='Studios', y='Total Shows', title='Top 10 Studios by Total Shows')
   fig.show()
   ```

7. **Top 4 Sources**
   - Created a pie chart to show the distribution of the top 4 sources of anime.
   ```python
   fig = px.pie(top_4_sourses_df, names='Source', values='Total Show', title='Distribution of the top 4 Sources by num of Shows')
   fig.show()
   ```
