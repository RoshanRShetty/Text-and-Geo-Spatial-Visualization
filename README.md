#Projext 2: Text and Geo Spatial Visualization

Please click to watch the overview video.

[![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/main.png)](http://roshanrshetty.github.io/Project2.1/Images/report.mp4)

**Visualization Link:** http://roshanrshetty.github.io

## Data Preprocessing:

The data sets used for the visualization were from the 'WikiNews' and 'Huffington Post' websites.
The same approach was used for both the dataset for preprocessing.

Preprocessing in various phases as explained below:

1. **Getting Frequency Count For Every Word** : In this phase,
    - we read all the records avaiable in the datasets,
    - parse the extract words,
    - keep a counter for each word, that increments when the same word appears again.
    - Then we allow the user to download the same processed data as a .csv file using the 'FrequencyCounter - huffington.html' or 'FrequencyCounter.html' pages.
    
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/preprocessing1.png)

2. **Getting All Record Numbers In Which A Word Appears** : In this phase,
    - we read all records in the dataset row by row,
    - for every word in the dataset, make seprate word entries with the record number.
    - if the same word is repeated in another row, we add the new record number to the already exisitng list.
    - then we allow the user to download the same processed data as a .csv file using the 'WordsInBlogs - huffington.html' and 'WordsInBlogs.html' pages.
   
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/preprocessing2.png)    

3. **Indexing** : To make processing the faster, we have implemented an index for all the words. The Index has been implemented using elasticlunr.js. for searching relationships we make use of this index.
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/indexing.png)

## Visualization:
The preproceesed data is presented in three ways:
### Wordle
A wordle(word cloud) is used to show all the main words asit is an effective way to visualize text with out any text overlapping.
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/wordle.png)

#### Main Features of the Dynamic Wordle Implemented:
- Words grouped according to categories.
- Words size is directly proportional to the frequency of the words.   
- Hovering over a word highlights other words related to it in the Wordle.
- The slider can be used to get the wordle for the corresponding month.
- The wordle for a specified time range can be generated based on the range specified by the use.
- ![ScreenShot](http://roshanrshetty.github.io/Project2.1/Wordle.PNG)
### Time Series Visualization using Stream Graph
- A stream graph is used to represent the frequency of words over the period of time in this visualization.
- Stream graphs are uniue, such that data is appended on top of existing data, with the y-value of the area under the curve at x being the actual value of the data, so data with a larger area underneath the curve means more frequent, and data with a smaller area underneath the curve means less frequent.
- The graph uses many ticks that span the width of the visualization, in order to help the reader understand values in the chart.
- To append data to the chart, simply double-click the text on the word cloud.
- The user may hover over the desired stream to highlight the stream, a tooltip will appear showing the word.
- The color of the stream corresponds to the category of word from the word cloud
- To remove the data from the stream, the user can double-click on either the desired stream or double-click on the word in the word cloud to remove it.
- Implementation with various categories is shown below.
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/Screen Shot 2016-11-11 at 1.56.20 PM.png)
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/Screen Shot 2016-11-11 at 1.57.54 PM.png)
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/Screen Shot 2016-11-11 at 1.58.20 PM.png)

### Force Directed Graph
A force directed graph is used to show the relationships between the nodes.
####Main Features of the Force Directed Graph Implemented:
- The relationships between words for the selected categories and time intervals are implemented.
![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/Force directed graph.PNG)

## Findings:

1. **Various Clusters Among Words Can Be Identified From The Relationship Graph** : The Force Directed graphs allows us to see patterns or clusters among words. These clusters can be used for 'Topic Analysis'![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/corelation.PNG)
2. **Presidential Elections and Candidates Are Visible From the Stream Graph** : In this example, you can see how John McCain as well as Barack Obama were mentioned frequently during the election cycle ![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/Screen Shot 2016-11-11 at 2.40.36 PM.png) ![ScreenShot](http://roshanrshetty.github.io/Project2.1/Images/Screen Shot 2016-11-11 at 2.41.14 PM.png)



