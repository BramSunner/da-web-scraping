# ds-web-scraping
Module 11 Challenge for DATA-PT-EAST-APRIL-041524-MTTH.


# About the Project
This project contains two modules: the Mars News notebook, and the Mars Weather notebook.  

## Mars News

This module scrapes a 'Martian news website' and stores the scraped data into a list of dictionaries.  
First, I use selenium with splinter to open the browser and extract the html for the site.  
Then, I use BeautifulSoup to create a soup object from the extracted html in order to grab the elements that I need.  
Last, I loop thru the soup object grabbing all of the article titles and previews and storing them into a list of dictionaries.  

## Mars Weather

This module scrapes a website containing 'Martian weather data from the curiosity rover' and uses it for analysis.
In this module, I first use selenium with splinter to open the website and extract the html.  
Again, I use BeautifulSoup to create a soup object of the extracted html.  
Then, I find all of the table rows within the html and store them into a variable 'rows'.  
Afterwards, I loop thru the rows and create a list of dictionaries matching the table presented on the website.  
After storing the table as a list of dictionaries, I create a pandas DataFrame from the data.  

Once I have the DataFrame created, I begin the analysis of the data.  
1. How many months exist on Mars? - I answer this with a unique count of the months represented in the data.  
2. How many Martian days' worth of data are there? - I answer this with a count of the rows in the dataset, considering each entry is from a unique day, this gives the amount of days represented in the observations.  
3. Which month, on average, has the lowest temperature? The highest?  

This question is answered via grouping the data into months and calling for the average temperature.  
Afterwards, I create a barchart represented the data to visualize the answer.  
4. Which month, on average, has the lowest atmospheric pressure? The highest?  

This question is answered, again, by grouping the data via month and calling for the average pressure.  
I create another barchart representing the data to visualize the answer.  
5. How many terrestrial days exist in a Martian year?  

For this question, I attempt a visual estimate via plotting the daily temperature on Mars on a scatterplot.  
Using the visualization, I attempt to find the 'repeating point' of the data (i.e: the point where I belive the yearly temperature starts the next cycle).  
Using this method, I found an average of 650 days in a Martian year.  
However, I had another avenue to estimate the amount of days in a year on Mars.  
I make two lists: one containing entries where the solar longitude of Mars is 0 and one where the solar longitude of Mars is 359 and fill the lists with the appropriate entries.  
I create another list that is empty so that I can store the results of the calculations.  
Then, I loop thru the two lists of data and create ranges with the following logic:   
1. First, check that the start ID (row number) is greater than the prior start ID and end ID.  
2. Second, check that the end ID is greater than the last end ID and start ID.  
3. Afterwards, a proper range is created using the start ID row as the beginning of the range, and the end ID row as the end.  
4. I grab a timedelta of the terrestrial date of each entry and store that into the results list.  

After running the calculation, I end up with a results list containing two values, both of which are 685 days.  
Using this method, I arrive at the estimate of there being 685 Earth days in a Martian year.  

# Built In  
Python.  
Jupyter Notebook.  
