# Homework1: Professionalism & Reproducibility

## About the project
The goal of this project is to construct, analyze, and publish a dataset of monthly article traffic for a select set of dinosaur pages from English Wikipedia from July 1, 2015 through September 30, 2022

## Data Source
This project access page view data using the [Wikimedia REST API](https://www.mediawiki.org/wiki/Wikimedia_REST_API) ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews), [endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)).

## License
Wikimedia Foundation REST API [Terms of Use](https://foundation.wikimedia.org/wiki/Terms_of_Use/en) and [Privacy Policy](https://foundation.wikimedia.org/wiki/Privacy_policy).

## Intermediate Data
There are three intermediate Json data file contains page view data with different access types: desktop, mobile-app, mobile-web:

[monthly_desktop_201507-202209.json](/IntermediateData/monthly_desktop_201507-202209.json)

[monthly_mobileapp_201507-202209.json](/IntermediateData/monthly_mobileapp_201507-202209.json)

[monthly_mobileweb_201507-202209.json](/IntermediateData/monthly_mobileweb_201507-202209.json)

variables and description:
- project: project name (en.wekipedia)
- article: article name (name of dinosaur)
- granularity: monthly
- timestamp: year, month, day, hour from July 2015 to Sept 2022
- agent: user
- views: number of page views
- access: type of access (desktop, mobile-app, mobile-web)

## Data Output
There are three output Json data file for desktop, mobile, and cumulative (desktop + mobile, and cumulative over months)

[dino_monthly_desktop_201507-202209.json](/DataOutput/dino_monthly_desktop_201507-202209.json) : views by article names with desktop access

[dino_monthly_mobile_201507-202209.json](/DataOutput/dino_monthly_mobile_201507-202209.json) : views by article names with mobile access

[dino_monthly_cumulative_201507-202209.json](/DataOutput/dino_monthly_cumulative_201507-202209.json) : views by article names cumulatively with desktop and mobile access

variables and description:
- project: project name (en.wekipedia)
- article: article name (name of dinosaur)
- granularity: monthly
- timestamp: year, month, day, hour from July 2015 to Sept 2022
- agent: user
- views: number of page views
- cumulative views (only for the cumulative output): cumulate number of page views

## Graphical Output

![Top_10_Peak_Views](/GraphicalOutput/Top_10_Peak_Views.png)

![Fewest_Months_of_Data](/GraphicalOutput/Fewest_Months_of_Data.png)

![Max_Avg_Min_Avg](/GraphicalOutput/Max_Avg_Min_Avg_.png)

## known issues or special considerations
- The Pageviews API requires not exceed 100 requests per second, a delay might be needed
