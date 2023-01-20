# UK Deaths by Vaccination Status

This notebook plots the May 2022 dataset from https://www.ons.gov.uk/peoplepopulationandcommunity/birthsdeathsandmarriages/deaths/datasets/deathsbyvaccinationstatusengland.
Curiously they stopped reporting the data, so let's take a look at it.

The .xlsx contains a bunch of tabs, but the interesting one contains standardized numbers per 100,000 which is what you need to do if you want to compare the numbers.  So we take "Table 3" which is "Whole period age-standardised mortality rates by vaccination status for all cause deaths, deaths involving COVID-19 and deaths not involving COVID-19, per 100,000 person-years, England, deaths occurring between 1 January 2021 and 31 May 2022".

Then this code pivots on vaccination status so we can pull out the data for Unvaccinated and compare that with all the other kinds of vaccination status they break out, which are:

- First dose, less than 21 days ago
- First dose, at least 21 days ago
- Second dose, less than 21 days ago
- Second dose, between 21 days and 6 months ago
- Second dose, at least 6 months ago
- Third dose or booster, less than 21 days ago
- Third dose or booster, at least 21 days ago
- Ever vaccinated

Now what I don't understand is that 'Ever vaccinated' should essentially be showing the average of all the other columns, but as you can see below it is not.  I computed the average myself (see the last chart) and it does not match.  The other problem with this kind of "averaging" is that one of the vaccinated groups named "Second dose, at least 6 months ago" cannot start until halfway through 2021 by definition, so it starts with all zeros, and those zeros are artificially pulling down the average for the vaccinated group.  So what we really have to do is look at all the charts and they all look pretty bad, except "Third dose or booster, at least 21 days ago" but even that is converging with unvaccinated by May 2022 when the data stops, and I suspect it crossed that path and is now much worse also which is probably why they stopped tracking it.

When you look at all the charts, it also shows many of these vaccinated groups are doing very poorly.

Plotting data from https://www.ons.gov.uk/peoplepopulationandcommunity/birthsdeathsandmarriages/deaths/datasets/deathsbyvaccinationstatusengland

See [Graphs](graph.html).