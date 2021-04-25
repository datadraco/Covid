# Assignment 2: COVID
This repository contains code and analysis of COVID-19 cases in the United States, using data from [The New York Times](https://github.com/nytimes/covid-19-data/).


## Analysis Reflections

**Q: What does each row in each of the data sets represent?** <br>

A: In the `national_df` each row represents a state total of cases and deaths (probable and confirmed) that have been reported through the end of that day. In the `state_df`, each row represents a day-state-FIPS total count of cases and deaths (probable and confirmed) through the end of that day. In the `county_df` each row represents a day-state-county-FIPS total count of cases and deaths (probable and confirmed) through the end of that day. <br>

**Q: What does each feature in the data set represent?** <br>

A: The `national_df`, `state_df`, and `county_df` share features that represent coronavirus `cases` and `deaths` that contain the total tallies of covid cases and deaths respectively through the end of that day. The counts include _probable_ and _confirmed_ cases combined, as defined by the Council of State and Territorial Epidemiologists. Both data sets also share a `date` feature that represents the day of the given data. The `state_df` and `county_df` have two additional features, `state` and `fips` that give the name of the state that the data is from and the FIPS of that state (FIPS is a standard geographic identifier that makes it easier for an analyst to combine this data with other data sets like a map file or population data). The `county_df` has one additional `county` feature that splits the data even further to represent which county in each state the data is coming from. <br>

**Q: Why do the data sets have different features?** <br>

A: The `national_df` data frame is aiming to give a top-down perspective of the covid situation across the entire U.S. as a whole, whereas the `state_df` contains two additional features so that it can give a more detailed and nuanced look at the situation by specifying total case counts in individual states on given dates, and the `county_df` zooms in even further to show which county from each state the data is coming from. <br>

**Q: What did you learn about the data set when you calculated the state with the lowest number of cases (and what does that tell you about testing your assumptions of a dataset?)** <br>

A: After calculating the state with the lowest number and finding that ``"Northern Mariana Islands"`` was the result, that shows me that the data set is taking more than just the expected 50 states into account. In general, this tells me that I should explore my data set a bit more before making any assumptions or making comparative calculations (like checking to see if there are only 50 rows representing states for every date entry). This is important to take into account when doing studies on big topics like covid where I may be posting and sharing analysis, so I would want to be sure to either filter out the observations that I did not want in the data set or clearly make a disclaimer about my data set being different than what might be expected. <br>

**Q: Is the location with the highest number of cases the location with the most deaths? If not, why do you believe that is so? What does this imply about whether features can "substitute" for one another in analysis?** <br>

A: No it is not the same, the county with the highest cases is Los Angeles but the county with the highest deaths is New York City. This could be for a lot of reasons (health care infrastructure, population density/size, average income of pop., etc.) but it would be hard to put a finger on one thing. This implies that features could not "substitute" for one another directly and represent the same data or analysis, but rather provide a separate perspective on the same issue or topic. Combining multiple different features (and creating more) to get a more nuanced and detailed picture of what's happening is probably the better way to go rather than isolating one feature as the "best" or stand-alone piece of analysis.

**Q: What do the plots of new cases and deaths tell you about the "waves" of the pandemic? How do the plots look different, and why do you think that is?** <br>

A: The waves of the pandemic have seemed to come at 3 distinct times, with a steep incline followed by a slight decrease which eventually leads to the next wave. This is particularly clear in the `new_cases_plot` where you can see the same pattern occur 3 separate times at an increasing scale over time. The death waves seem to lag behind a bit, and seemed to particularly spike early on (most likely because we were not as good at treating it). It is interesting that the second wave of new cases did not get mirrored the same way on the deaths plot, but the first wave most likely saw a lagged spike in deaths due to lack of awareness and preparedness (overflowing hospitals) and the third wave is seeing a spike due to the sheer number of cases overwhelming the healthcare system.

**Q: What do you notice about the values in `lowest_case_locations_by_state`? Consider both the names of the counties as well as how many there are.** <br>

A: There are several counties that are marked as "Unknown", which really clouds the data set and the analysis you could draw from it, especially because of how many of these entries look that way. I also noticed at least one occurrence of a repeat county from `highest_case_locations_by_state` in the District of Columbia.

**Q: What surprised you the most throughout your analysis?** <br>

A: I think what was surprising to me the most is the accuracy of the data all the way down to the county level. Considering that there have been 3M+ cases it's surprising to me that the county level data does not have more discrepancies with the national data. Also, it's pretty shocking to see that we're really still in the worst of it, I've stayed up to date with a lot of the covid data and visualizations (because I think they're really interesting even though they are quite depressing) but seeing that the most new deaths was as recent as this week is pretty brutal.
