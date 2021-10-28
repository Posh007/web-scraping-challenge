# Web Scraping Homework - Mission to Mars

![mission_to_mars](https://images.theconversation.com/files/13860/original/xvt334wf-1344146739.jpg?ixlib=rb-1.1.0&q=45&auto=format&w=926&fit=clip/)

In this assignment, we will build a web application that scrapes various websites for data related to the Mission to Mars and displays the information in a single HTML page using the steps below: 

## Step 1 - Scraping

The initial scrapping task was completed using Jupyter Notebook, BeautifulSoup, Pandas, and Requests/Splinter.

### NASA Mars News

* Scraped the [Mars News Site](https://redplanetscience.com/) and collected the latest News Title and Paragraph Text, as well as assigned the text to variables.

### JPL Mars Space Images - Featured Image

* Used splinter to navigate the Featured Space Image site [image](https://spaceimages-mars.com).

### Mars Facts

* Used Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc. from the Mars Facts webpage [here](https://galaxyfacts-mars.com) and 
* Also used Pandas to convert the data to a HTML table string.

### Mars Hemispheres

* Obtain high resolution images for each of Mar's hemispheres from astrogeology site [here](https://marshemispheres.com/) to .
* Saved both the image url string for the full resolution hemisphere image, and the Hemisphere title containing the hemisphere name. Used a Python dictionary to store the data using the keys `img_url` and `title`.
- - -

## Step 2 - MongoDB and Flask Application

Used MongoDB with Flask templating to create a new HTML page that displays all of the information that was scraped from the URLs above.

* The Jupyter notebook was converted into a Python script called scrape_mars.py with a function called scrape  to obtain one Python dictionary containing all of the scraped data.

* Set up a route called `/scrape` to import `scrape_mars.py` script and initialize  the`scrape` function.

* The /data route queries the Mongo database and passes the Mars data into an HTML template for display (data.html).

* Stored the return value in Mongo as a Python dictionary.

* Created a root route `/` that queried Mongo database and passed the mars data into an HTML template to display the data.

* Created a template HTML file called `index.html` stode in "templates" folder that will take the mars data dictionary and display all of the data in the appropriate HTML elements. 

- - -

## Step 3 - Submission

Included in this repository are the following:

1. The Jupyter Notebook containing the scraping code used.

2. Screenshots of the final application.
