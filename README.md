DATA WRANGLING CHALLENGE REPORT

Position: Junior Software Engineer.
Name: Henriette Dusabimana

Expected outcome: git repository with dataset and script

This is the link to the ipynb google file in order to view the the plots that have some insights: https://drive.google.com/file/d/1NjQJX0q3dWfXERUyxFA6ErNyEgWdlCSw/view?usp=sharing
Open it using Colaboratory.

Subimission data: 15th July 2021

STEPS FOLLOWED WHILE WRITING THE SCRIPT THAT PRODUCED THE NORMALIZED DATASET

- Install BeautifulSoup in the same folder where you are going to run your project using this command
  pip install beautifulsoup4 
  
1. Import libriaries to be used 
 - BeautifulSoup
 - requests
 - csv
 - re 
 - pandas 
 - numpy 
 - seaborn 
 - matplotlib
 
2. Save the url website that has the table we want to normalize in a variable 

3. Make a GET request to fetch the raw HTML content 

4. In order to be able to extract data from the html content, we have to use the library BeatifulSoup

5. Use the results given by beautifulsoup and extract the htlm table, Lucky for us the first table within class wikitable was the one we were looking for 


6. Get the headings of the table by looping through the th elements of the html table and save them in an array 
    
7. Use some regex to remove unnecessary characters in each heading before saving it in the array 
   - td.text.replace('\n', ' ').strip(): this is to remove \n that is inserted at the end of each line
   - re.sub("[\(\[].*?[\)\]]", "", td): this is to remove the texts that are enclosed between () and [] in the headings
   - re.sub('[0-9]', '', td): this is to remove the year number on some headings
   - re.sub('in', '', td): this is to remove the word "in" at the end of some headings
   
8. When the heading is ready, save is in the array of headings   

9. Loop through the content of rows in the same table from Beautifulsoup and save the text content of each of them in the array but zip them along with the corresponding header.

10. Convert array of data into dataframe 

11. Remove the rows that have NAN values using dropna() 

12. Add the year row with 2018 as the year

13. Delete the last row of totals before sorting the dataframe 

14. Save the data in a new variable 

15. Make some cleaning in the columns data from each column before saving the data in CSV or ploting

16. Save the unsorted data in a CSV file called unsortedresults.csv in case you want to use it in the future

17. Sort the data by “Road deaths per Million Inhabitants" 

18. Reoder the columns of the dataframe 

19. Save the dataframe as a csv file called results.csv

20. Plot GDP per capital by country using the function of seaborn called barplot, pass country as the x axis variable and the GDP per capital as the y axis, the rest are specifications of the figure. 
 
 The resulted figure can be found on the shared google doc. 

- COMMENTS ABOUT THE FIGURE: 
* Luxembourg, Ireland, and Danemark were the top 3 countries with good GDP while Belgium and Romania were the last two countries in 2018 in terms of their GDPs

21. The next figure is  Population for each country using the function of seaborn called barplot, pass country as the x axis 
variable and the population as the y axis.

- COMMENTS ABOUT THE FIGURE: 
 * Germany, France, and UK were the top 3 most populated in Europe in 2018
 * Malta and Luxembourg, and Cyprus were the last 3 less populated countries in Europe in 2018

22. Another figure that was ploted is European Union Vehicle ownership & Population density by country in 2018.

- COMMENTS ABOUT THE FIGURE: 
 * The reason to combine the two was to see the ownership of cars compared to how the place is populated
 * As you recall from the previous figures, Malta and Luxembourg, and Cyprus were the less populated countries, which means more space probably, so as the country is less populated the more cars its population owns.
 
23. The last plot is the same as the provious one, the difference is that we calculated the ratio as Vehicle Ownership per Capita  and plot it as one element on the plot. 

