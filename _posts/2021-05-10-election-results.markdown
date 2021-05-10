---
title: ":ballot_box: 2012 Election Results Searcher :ballot_box:"
layout: post
tag: Java Project
date: 2021-05-10
image: 
headerImage: false
projects: true
hidden: false
description: 2012 Election Results Search
category: project
author: treymorris
externalLink: false
---

## What is this project about?
This project was my first data source project. This project was a final project for my AP Computer Science class. My goal was to read data from a CSV file and use the data from that file and return certain pieces of information from the file to a user when called. I decided to do my project over the 2012 election and return results based on county and state from user input. I chose this election in particular, because it was one of the first real elections I remember. I was in 4th grade and probably around 9-10 years old when this election happened and I remember lots of news coverage and conversation about this election even at my young age. 


### What library/libraries did I use for this project?
This was my first use of external libraries within java. With this project I used the sinbad software library that is used for Java, but also for other languages like Python and Racket. The project uses online data sources and offline data sources such as CSV, JSON, and XML files in order to read and parse data to be used for software. 



### More about the project.
In this project, I used two main classes, the main DataProject.java file and the Results.java file. The DataProject.java file contains the main method and the Scanner object that intakes user input where you can input the county name and state abbreviation. This is to be able to give a more and precise result when the program is used and return the election data. The documentation from the Sinbad library to complete this project and how to use methods from the library. 

#### A snip of code from the project can be found below.

{% highlight java %}
// This is the import of the .csv file and loading it into the program
DataSource electionResults = DataSource.connect("lib/us-election-2012-results-by-county - us-election-2012-results-by-county.csv");
        electionResults.load();
// This is where the information is stored in an ArrayList using a method from the sinbad library ."fetchList"
 ArrayList<Results> results = electionResults.fetchList("Results","FirstName","LastName","Party","CountyName","StateCode","Votes");


{% endhighlight %}

#### A second snip of code showing my usage of a for-each loop with two if statements nested within it.
{% highlight java %}
//For-Each loop with el being short for elements
for (Results el : results) 
        {
            if (el.isLocatedInCounty(county))
            {
                if (el.isLocatedInState(state))
                {
                    /*Return the method calls from second class Results.java that candidate name, party name,
                    vote county along with the county name and state name from user input. */
                    System.out.println(el.getName() +" Representing the " + el.partyAbrev() + " party received " + el.getVoteCount() + " votes in " + el.countyName() +" County, in the state of " + el.stateName() + " in the 2012 election.");
                }


{% endhighlight %}



### Conclusion


This lab was called the DataLab and included basic topics of Data Science and the how it connects with modern day techonology and the studies of Computer Science.
More about the lab can be found [here](https://apcentral.collegeboard.org/pdf/ap-computer-science-a-data-lab-student-guide.pdf)




####Links to 
Sinbad can be found [here](http://berry-cs.github.io/sinbad/).
The .csv file used for data can be found [here](https://data.world/aaronhoffman/us-general-election-2012)


---



---

Check out the project on github(https://github.com/TreyBMorris/2012GeneralElectionResultsSearch) [here].
