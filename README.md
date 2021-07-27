# Web Scraping Homework - Mission to Mars

![mission_to_mars](Images/mission_to_mars.png)

In this assignment, we will build a web application that scrapes various websites for data related to the Mission to Mars and displays the information in a single HTML page. 

1. Notebook/script `mission_to_mars.ipynb` with all scraping and analysis tasks; and flask app are contained in a folder: **Missions_to_Mars**.

## Step 1 - Scraping

The initial scrapping task was completed using Jupyter Notebook, BeautifulSoup, Pandas, and Requests/Splinter.

The following outlines were followed.

### NASA Mars News

* Scraped the [Mars News Site](https://redplanetscience.com/) and collected the latest News Title and Paragraph Text, as well as assigned the text to variables.

```python
# Example:
news_title = "NASA's Next Mars Mission to Investigate Interior of Red Planet"

news_p = "Preparation of NASA's next spacecraft to Mars, InSight, has ramped up this summer, on course for launch next May from Vandenberg Air Force Base in central California -- the first interplanetary launch in history from America's West Coast."
```

### JPL Mars Space Images - Featured Image

* Visited the url for the Featured Space Image site [here](https://spaceimages-mars.com).

* Used splinter to navigate the site and find the image url for the current Featured Mars Image and assign the url string to a variable called `featured_image_url`.

* Ensured to find the image url to the full size `.jpg` image and saved  a complete url string for the image.

```python
# Example:
featured_image_url = 'https://spaceimages-mars.com/image/featured/mars2.jpg'
```

### Mars Facts

* Visited the Mars Facts webpage [here](https://galaxyfacts-mars.com) and used Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc.

* Used Pandas to convert the data to a HTML table string.

### Mars Hemispheres

* Visited the astrogeology site [here](https://marshemispheres.com/) to obtain high resolution images for each of Mar's hemispheres.

* Clicked each of the links to the hemispheres in order to find the image url to the full resolution image.

* Saved both the image url string for the full resolution hemisphere image, and the Hemisphere title containing the hemisphere name. Used a Python dictionary to store the data using the keys `img_url` and `title`.

* Appended the dictionary with the image url string and the hemisphere title to a list. This list will contain one dictionary for each hemisphere.

```python
# Example:
hemisphere_image_urls = [
    {"title": "Valles Marineris Hemisphere", "img_url": "..."},
    {"title": "Cerberus Hemisphere", "img_url": "..."},
    {"title": "Schiaparelli Hemisphere", "img_url": "..."},
    {"title": "Syrtis Major Hemisphere", "img_url": "..."},
]
```
- - -

## Step 2 - MongoDB and Flask Application

Used MongoDB with Flask templating to create a new HTML page that displays all of the information that was scraped from the URLs above.

* Converted Jupyter notebook into a Python script called `scrape_mars.py` with a function called `scrape` to obtain one Python dictionary containing all of the scraped data.

* Set up a route called `/scrape` to import `scrape_mars.py` script and initialize  the`scrape` function.

* Stored the return value in Mongo as a Python dictionary.

* Created a root route `/` that queried Mongo database and passed the mars data into an HTML template to display the data.

* Created a template HTML file called `index.html` stode in "templates" folder that will take the mars data dictionary and display all of the data in the appropriate HTML elements. 

![final_app_part1.png](Images/final_app.png)

- - -

## Step 3 - Submission

Included in the submission are the following:

1. The Jupyter Notebook containing the scraping code used.

2. Screenshots of the final application.

3. Link to the new repository submitted to BootCampSpot.