# Netflix EDA — Exploratory Data Analysis

## Overview
Analysis of 8,800+ Netflix titles using Python to uncover content trends 
across growth, geography, and audience ratings.

## Tools
Python · pandas · seaborn · matplotlib · Jupyter

## Questions Answered

1. How has Netflix's content grown year over year?
2. Which countries produce the most content?
3. How are content ratings distributed?

## Key Findings

1. At the beginning of the streaming age of Netflix (around 2007/2008) there was only a modest 50 movies and shows available. From then, it wasn't until 2015 when we saw a growth in that number, all the way to 84. From 2015 to 2016, there was a 4x boom, with 428 content available, and from 2016 to 2017, another ~3x boom with 1186 contents available. 2019 had the highest peak of content available, and that number was 2016 shows and movies. The growths of netflix's content year of year makes sense according to digital entertainments timeline, as the mid/late 2010s is known as the "streaming wars" era, where major digital entertainment studios released individual streaming services such as HBO, MAX, Disney +, HULU, and more, making Netflix increase their catalog as to increase thier competitve edge.
---

2. With the help of some code:

```Python
top_12_pct = {}
for country in countries[countries != 'Unknown'].value_counts().head(12).index:
    pct = df['country'].str.contains(country, na=False).sum() / len(df) * 100
    top_12_pct[country] = round(pct, 2)

top_12_pct
```
 We can see that 41.9% USA, 11.88% India, 9.15% United Kingdom, 5.05% Canada, and 4.46% France as the top 5 producing countries.

 <img width="1078" height="693" alt="Screenshot 2026-10-07 at 1 52 06 PM" src="https://github.com/user-attachments/assets/3d3d12a8-6253-43fc-9e90-ca2a7e26b7e6" />
 
 ---
 

3. From the figure below, we can see the biggest rating shown is TV-MA (mature), followed by TV-14, TV-PG, R, and PG-13 to round out the top 5. TV-MA and R are essentially the same rating given out to titles, but TV-MA is reserved only for TV shows, while R is reserved only for Movies.

<img width="850" height="574" alt="Screenshot 2026-10-07 at 1 55 49 PM" src="https://github.com/user-attachments/assets/98f73041-bddc-43a6-b1d2-aab8178f5e58" />

## How to Run
1. Clone the repo
2. Open Netflix_EDA.ipynb in JupyterLab
3. Run all cells
