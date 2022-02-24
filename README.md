# EAGLE
Code for the building of a metric called EAGLE which quantifies MLB hitter plate discipline

## Abstract

In this study, we use Statcast data from the 2017-2021 Major League Baseball seasons to quantify the ability of players to make correct decisions about whether or not to swing at each pitch. We named this metric EAGLE, which stands for Expected Additional runs Gained by Looking/swinging Estimate. Using player hitting statistics and pitch characteristics, we use an xgboost model to predict the likelihood of each possible outcome from a swing (Miss, Foul, Out, Single, Double, Triple, Homerun), and from not swinging (Ball, Strike). For each pitch, we calculate the change in run expectancy given the situation for each outcome. We then calculate the expected runs scored in the remainder of the inning by multiplying the run expectancy of each event by the probability that it is to occur given the pitch information metrics. We quantify a hitter's plate discipline by averaging the total increase in expected runs from each pitch thrown to that hitter. We show that this metric is stable over time, with a correlation coefficient of 0.43 from year to year. EAGLE also explains current year hitting performance, with a correlation coefficient of 0.371 with On Base Percentage. It explains swing decision making much better than current and commonly used statistics like O%. Additionally, EAGLE takes into account pitch movement and location within the zone to estimate how well pitches can be hit. As a result of this, EAGLE has a correlation of 0.459 with OPS. EAGLE accurately determines how good players are at choosing which pitches to swing at and can improve predictions of future hitting performance. It has better prediction of future OPS than other commonly used plate discipline metrics, like O% or K/BB ratio. 


## Data and File Info

You will need several data files to be able to run this code. All the data comes from the savant API using the baseballr package, 
but I have already condensed this data into rds files in order to make it faster and easier to run. Loading in the data from the api would take a long time. 
Here is the link to the folder containing the data files:
https://drive.google.com/drive/folders/1vbyZ-KhBOiYiO1HYJ4jrw4PXHgUuz8or?usp=sharing

In addition, I have included a PDF file that is what the output of the EAGLE.rmd should look like. This is found in "EAGLE Markdown Output.pdf"

The original paper can be read in EAGLE.pdf
The SABR updated version of the paper can be read in EAGLE SABR.pdf

## Shiny App
Here is a link to the shiny app for EAGLE as well: https://jmould77.shinyapps.io/EAGLE/
