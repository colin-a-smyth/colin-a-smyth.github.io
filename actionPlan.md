# Plan Of ACTION

## Plan from ReadMe.md

### Part 1
First, we want to focus on the Wikipedia articles about countries and their hyperlink structure in the Wikispeedia dataset:

- Q1: How different are the length of these articles and their number of hyperlinks?
- Q2: How positive or negative is the content of an article and the articles linked to it?

### Part 2

Second, we want to focus on the pathways that were taken by the players, where the target or goal article of the game is a country:

Q3: Is there a correlation between the ratio of finished pathways and the country?
Q4: Is there a correlation between the length of the pathway taken respectively the time needed and the country?

### Part 3
Third, we want to deepen the analysis by controlling for as many confounders as possible and answer the following questions:

Q5: By investigating article length, article sentiment or number of hyperlinks while controlling for e.g. population size, economic power or if English is an official language, is there a representation bias based on countries in Wikipedia?
Q6: While controlling for as much of the bias in the dataset as we can, do we see additional bias of the players in the pathways they have taken?

## New Plan !

### Notebook structure

- Loading data
- Data wrangling
- Data analysis
    - Part 1: Descriptive statistics and naive statistical analysis of the Wikispeedia Dataset
        * A: Exploratory data analysis
        * B: Length of the articles* and their number of hyperlinks
        * C: Sentiment analysis of articles*
    - Part 2: Descriptive statistics and naive statistical analysis about the behaviour of the players
        * A: How different is the ratio of finished pathways, where articles* are the start/target?
        * B: How different is the length of the pathway taken respectively the time needed, where articles* are the start/target?
        * C: How often does an article* appear in a pathway where it is neither the start nor the traget?
    - Part 3: Analysis of biases
        * A: Establish baseline (e.g. expected length for world mean population or economic strength)
        * B: By investigating article length, article sentiment or number of hyperlinks while controlling for e.g. population size, economic power or if English is an official language, is there a representation bias based on countries in Wikipedia?  
        * C: While controlling for as much of the bias in the dataset as we can, do we see additional bias of the players in the pathways they have taken? -> culutral bias (how much do players know about countries, since we can not conclude anything without demographic informations about the players)

### Our Plan

1. Introduction
    - Show why this is important.
    - Short text to introduce dataset
    - **Flourish map** to present the dataset and the regions that we will refer to, the income bands, and population size. @Blanche
    - Small sentence to present the countries, say what is important to remember from the map.
        - Uniformly distributed number of countries in each income band.

2. Article Lengths
    - Histogram with error bars or a box plot to display the length of the aritcles by region.
    - Want to show that countries are not equally represented by the article length.
    - Or we could use a heatmap of the world, darker colour for longer articles.
    - Key outcome: length can be super important for bias for an LLM. There is a clear bias (we hope!!)
    - Bias also towards high income countries (notable because balances dataset).

3. Hyperlinks
    - Small text to interoduce hyperlinks: how they are important; what they mean in the game.
    - Keep histograms but with regions on the y-axis for readability.
    - Add error bars (95%).
    - Include dropdown menu for selecting in- or out-degree.
    - In each bar's description we want smaller details like actual number of links vs relative number of links.
    - We also must normalise by article length.
    - Key outcome: even if articles are normalised length some articles are more connected, but they are not normalised !
    - Do same graph again for economic region.
    - **Check mean/median**
    - Bubble graph perhaps for displaying links in and out, bubble size represents the number of links, clustered by region/income.

4. Sentiment Analysis
    - Few sentences to explain why we want to do sentiment analysis, and what the sentiment means for us.
    - We need to try another model, one that is more suited to this type of article (news perhaps, not tweets), and we need to add CI for each bar.
    - Depending on above results, differences in sentiment could be significant, and but also if not that is ok and we can discuss why this is good! (find paper discussing neutrality in wikipedia if it exists)
    - Link to part 2: user behaviour.
        - Small conclusion on the above and see if the biases are refelcted or reinforced by user behaviour.
        - Explain why this is important: How paths would be altered in LLM with thie information from player.
    - Note the limitations of the model.

5. Finished/unfinished paths
    - ~~Graph (like wikiwomen) with the proportions of finished and unfinished but done with plotly, hover for more details by region.~~
    - Results are obvious if we do not remove the confounder of article length/article with a lot of links.
    - Maybe there is human bias that is reinforcing the results but we cannot see.
    - Length/Time: Graph .....? 
    - Similar bias here based on length of articles.
    - Maybe we should describe the hubs, and see if the users do find the hubs (they do).
  
6. Occurances of a country in a path.

    - ~~Add error bars.~~
    - Representative of how players use the countries.
    - Should we remove the 'hubs' or match slightly better to get a real look at things?

7. Regression
    - Can we do a regression to see what factors actually influence the players pathways?

8. Ethics
    - Something short about ethics of analysing as we do.
    - Notes on how wiki articles are generated, and on who the editors are.

9. Conclusion
    - Dataset is biased towards high income countries and against places like Micronesia and Polynesia.
    - This dataset could work for an LLM for the US but not for other regions, should be considered before training a model!

### Tasks

- Colin
    - Plotly
    - Look at what actually requires error bars and what they would signify in context.

- Blanche
    - Flourish (and Plotly)



