# IPEDS Project

## About the Project

I pursued this project with the goal of demonstrating my ability to complete a data analysis/visualization project from beginning to end, with the final product being a set of Tableau dashboards.

You can find the dashboards at this link: <https://go.ncsu.edu/ipeds>

## About the Data

The data I used comes from the Integrated Postsecondary Education Data System (IPEDS). According to their website, IPEDS *is a system of interrelated surveys conducted annually by the U.S. Department of Education's National Center for Education Statistics (NCES). IPEDS annually gathers information from about 6,400 colleges, universities, and technical and vocational institutions that participate in the federal student aid programs.*

The data are available for bulk download at this link: <https://nces.ed.gov/ipeds/use-the-data/download-access-database>

You'll see that the data are broken up by year and are stored in Access databases. Each download also includes data documentation (you can see the data documentation for 2018-2019 here: [IPEDS201819Tablesdoc.xlsx](./IPEDS201819Tablesdoc.xlsx)).

I mainly utilized data from the academic library survey table (table name: AL[YYYY]). This table contains statistical data about collection size, collection circulations, interlibary loans, etc. I also grabbed student enrollment numbers from table EFFY[YYYY] and university names from table HD[YYYY].

You can view the fully-processed data here: [IPEDS_joined_export.xlsx](./IPEDS_joined_export.xlsx)

## The Process

1. **Data exploration.** I pulled down one of the database files and data documentation and did a deep dive into the documentation in order to see what tables and variables were available. This is when I identified the academic library data table and decided to run with analyzing that data. I decided that I wanted to compare several of the metrics from NC State to peer institutions like Iowa State University and Purdue, as well as see if there was any correlation at NC State between student enrollment and collection size.
2. **Data collection, aggregation, normalization.** The data I needed was strewn throughout multiple database files and tables within each database. First, I downloaded each of the database files for five-years-worth of data. Next, I built an upper Access database where I could create link tables that imported only the tables from the other databases that I cared about. Then, I designed an SQL query to join the data into a single table that I could export. Finally, I exported the data into a spreadsheet that I could upload to Tableau.
3. **Data analysis and visualization.** I uploaded the spreadsheet into Tableau and started playing around with different visualizations to see what stories the data might tell. After I identified a few visualizations, I created a dashboard for each and published them to Tableau Public.

Here are a few links related to the process:

- Example SQL query used to pull the data together: [accessSql_aggregate_query.sql](./accessSql_aggregate_query.sql)
- The upper database used to import tables from multiple database files. The specific database files were too big to upload to GitHub: [IPEDS_Aggregate.accdb](./IPEDS_Aggregate.accdb)
- Processed/exported data: [IPEDS_joined_export.xlsx](./IPEDS_joined_export.xlsx)

## Preliminary Findings and Visualizations

Link to Tableau dashboards: <https://go.ncsu.edu/ipeds>

There were four tasks or questions that I wanted to look at:

- How does NC State's library physical collections compare to peer institutions Iowa State University, Penn State University, Texas A&M, and Purdue?
- How does NC State's library collection circulations compare to peer institutions?
- How does NC State's library interlibrary loans provided to other institutions compare to peer institutions?
- Do student enrollment numbers at NC State correlate with physical collection size?

As I took a closer look at the data, I quickly realized most of the data was not going to be accurate enough to show any compelling comparisons. When you look at the visualizations you'll see that numbers like "total physical collections" and "total circulations" vary widely between some of the years, which when scrutinized under the lens of context should not be the case (I am happy to provide that context if there's interest). In any case, I decided to go ahead and create a few continuous line charts to demonstrate what a comparison visualization looks like.

Interlibrary loan numbers were fairly stable, so I was able to create a stacked bar chart to showcase this comparison.

Finally, I wanted to see if student enrollment numbers at NC State correlate with physical collection size. Unfortunately, because physical collection numbers were likely not very accurate, I was unable to draw any conclusions. However, I created a double line chart to demonstrate what this type of visualization looks like.
