<h1>Dinosaur Access Visualization</h1>
<h2>Bonaventure Raj</h2>



<h3>Objective</h3>
The main objective for this repository is to visualize user access data to Dinosaur articles on Wikipedia from July 2015 - Sept 2022 on a monthly basis. This pulls access data from different mediums including desktop, mobile-user, and mobile-web. From there, we navigate through three tasks to understand article access patterns via Time Series Visualizations.

<h4>Task 1</h4>
Task 1 visualizes a time series plot that contains the highest and lowest average page requests to a specific article for both mobile and desktop access. The timeseries then takes these four plots (highest desktop/mobile, and lowest desktop/mobile) and plots their views per month.

<h4>Task 2</h4>
Task 2 visualizes a time series plot that contains the top 10 most viewed article (found by the highest peak at any given month for a specific article) for both mobile and desktop access. The timeseries then takes these twenty plots (top 10 highest for desktop, and top 10 highest for mobile) and plots their views per month.

<h4>Task 3</h4>
Task 3 visualizes a time series plot that contains top 10 least visited article pages for both mobile and desktop access. The timeseries then takes these twenty plots (bottom 10 least accessed for desktop, and bottom 10 least accessed for mobile) and plots their views per month.



<h3>Source Data</h3>

This project retrieves all data from Wikipedia API which follows under the Creative Commons Attribution-ShareAlike License. As stated on [Wikipedia's Licensing Website](https://www.mediawiki.org/wiki/API:Licensing):

> All structured data from the main and property namespace is available under the Creative Commons CC0 License; text in the other namespaces is available under the Creative Commons Attribution-ShareAlike License; additional terms may apply.

These are the terms of use for this API: ([license](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)).

[Wikipedia API Documentation]('https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews')
[Wikipedia API endpoint]('https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end')


<h3>Project Files</h3>

This project contains with and produces several files. 

<h4>Contains</h4>
This project contains a few files that are necessary notebooks and csv's to run the task smoothly. The `dinosaur_genera.cleaned.SEPT.2022 - dinosaur_genera.cleaned.SEPT.2022.csv.csv` is a csv file that contains all dinosaur article names and their respective Wikipedia URL. We use this to parse for user data when making request to the Wikipedia API. The `get_data.ipynb` notebook is used solely to get and save data from the Wikipedia API. Lastly, the `visualize.ipynb` notebook contains all visualizations for tasks.

<h4>Produces</h4>

The `get_data.ipynb` notebook produces three json files `dino_monthly_cumulative_<201507>-<202209>.json`, `dino_monthly_desktop_<201507>-<202209>`, and `dino_monthly_mobile_<201507>-<202209>`. These JSON structured files contain all user access data on a monthly basis from July 2015 to Sept 2022 for each article in key-value pairs. The name of the file indicates the access type, for example, dino_monthly_desktop indicates all desktop access. Mobile indicates all mobile access. These are found in the `data/` directory

The `visualize.ipynb` notebook produces three png files `task_1.png`, `task_2.png`, and `task_3.png` which are visualizations created for each respective task found in the `visualizations/` directory.


<h3>Future Considerations</h3>
There are a few considerations to be made in reproducing this work in the future. Fistly, some of the article's may be deprecated or contain no access data. If so, this means that there is no data to query from the Wikipedia API for this article. This happens on two occasions during this project. Secondly, please keep in mind that the Wikipedia API does state to change the User Agent headers passed into the request. This allows for ease of access in tracking and accountability.



