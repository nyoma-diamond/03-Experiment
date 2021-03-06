# Assignment 3 - Replicating a Classic Experiment

N'yoma Diamond, Felix Chen, Luke Gebler

Github Pages/Survey Link: [https://nyoma-diamond.github.io/CS4802-03-Experiment/](https://nyoma-diamond.github.io/CS4802-03-Experiment/)

## Experiment

For our experiment we showed each participant 20 instances of each visualization. Starting with the pie chart, moving on to the box plots, and finally the bar chart. The box plots and bar charts were each marked with 2 dots, signifying which parts of the chart we want to compare. The pie chart was given different colors for each piece and a key was given to signify which slices should be compared.

## Visualizations

Each of the visualizations were generated randomly. This was done by generating an array with a random length within a range and then filling that array up with random values.

### Bar Chart

![Bar Chart](./img/bar.png)

Our bar chart was our best performing chart by a wide margin. This is similar to Cleveland & McGill's results, as it is easiest to compare two bars height as oppose to other visualizations.

### Pie Chart

![Pie Chart](./img/pie.png)

Our pie chart was significantly worse in performance compared to the bar chart, but beat out box plots by a small margin. While the majority of pie chart data had only a small amount of error, it had significantly more drastic outliers compared to the bar chart.

### Box Plots

![Box Plots](./img/box.png)

Box plots were the worst performing chart out of the three. This could be for a couple reasons, our first theory is the lack of knowledge about how to read a box plot. Some people may have factored in the tail into their calculations while others did not. Secondly, box plots could overall be harder to compare sizes due to the lack of allignment between each box. This caused for a wide variability in answers, creating more outliers compared to the other two charts.

## Results

![Error CI Plot](./img/conf-int.png)

As you can see here, our bar chart results are quite similar to the Cleveland and McGill results. However, our pie chart results were slightly worse than Cleveland and McGill with a larger spread as well. Looking at their methodology, it looks like they labeled their slices with letters at each slice's midpoint and their slices were all pretty large. These factors could have led to improved graphical perception compared to our study where we only limited the size of our pie chart slices when they became close to imperceptible.

Bootstrapped 95% confidence intervals are as follows:

| Chart Type |   Lower  |   Mean   | Upper    |
|:----------:|:--------:|:--------:|----------|
| Pie Charts | 2.221697 | 2.438320 | 2.634616 |
| Box Plots  | 2.304273 | 2.555572 | 2.785398 |
| Bar Charts | 1.155991 | 1.373288 | 1.577383 |

### Flourish Visualization

![Flourish](./img/Size_Comparisons.png)

This visualization helps show how certain visualizations performed better than the other as it plots each individual data point on a graph. Barcharts appear to follow the trendline no matter the differentiation in height. Pie charts seem to be harder to read the smaller the actual difference between the slices are, while box plots seem to struggle on the other end of the graph, where the actual difference is greater. An interactive version of this visualization is accessible [here](https://public.flourish.studio/visualisation/5397388/).

## Achievements

### Technical

- We implement box plots as one of our visualizations, a much harder to implement chart compared to others
- Instead of locally storing the data, we used the online service "Formspree" to gather and compile all of our data allowing us to easily export it as a csv to do analysis on
- All of our data is completely randomly generated with both the amount of slices/bars/boxes and their values being random
- We have a lot of JavaScript in our project which enabled our entire survey to be taken from one webpage without our users ever having to load or navigate to another page

### Design

- We added some formatting and css to make the webpage more user friendly. Some of these features included centering text and images on the webpage, adjusting font and text size, and adding some color to text
- We also added a question counter so that users could see how many questions they had completed and how many were remaining
- To mark the pie charts, we colored every slice of the pie chart so that no slices in particular stood out. This eliminated the need to mark the slices with dots or other markers which presented issues such as possibly giving the users another item to aid their comparison of the two slices
- The pie chart uses a color-blind friendly color pallete so color blind users aren't affected when taking our survey
- Additionally, we added color circles for each of our pie charts so that it was easy for users to tell which of the pie slices we wanted them to look at. This eliminated to need to describe colors in writing, which would end up being complicated with colors such as blue and cyan
- The pie charts also had a minimum slice value, since as slice values approached zero, it became impossible to tell what color a slice was due to the strokes covering the entire slice
- For the bar charts and box plots, we added dots at the bottom of the objects we wanted the users to compare. This followed the Cleveland and McGill example and provided an easy way to mark the objects without affecting the users' graphical perception of the objects
