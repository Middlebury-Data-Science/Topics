Shiny for Interactive Apps
========================================================
author: Albert Y. Kim
date: Friday 2016/3/25




Intro to Shiny
========================================================

Today we will create **interactive** web applications via Shiny.  Shiny allows
you to do so without knowing HTML, JavaScript, CSS, etc...

For the rest of this talk, if you see `USERNAME`, replace this with your
Middlebury login.



Chief Components
========================================================

There are two chief components building a Shiny app:

* `inputPanel`:  Where your app takes **inputs** and stores them in an object
called `input`.  Ex: text, numerical values, sliders, radio buttons, etc.
* `renderSOMETHING`: After processing the inputs and data, Shiny **renders** an
output: plots, table, text, etc.





Create New Shiny App
========================================================

We won't be harnessing the full power of Shiny (i.e. using `server.R` and `ui.R` files),
but rather a simplified version using R Markdown.






Example:  Input Panel
========================================================

The `inputPanel( ... )` section takes in two inputs (separated by a comma):

* `selectInput()` which assigns a value to `n_breaks` based on a selection menu, formats the input box, and selects 20 as the default option.
* `sliderInput()` which assigns a value to `bw_adjust` based on a slider, formats the input box, and sets 1 as the default value.





Example:  Input Panel
========================================================

Note:

* All possible `inputPanel()` options are listed in "Widgets" on the cheatsheet.
* Type `?selectInput`, for example, to get a sense for the arguments.





Example:  Rendering Output
========================================================

The `renderPlot({ ... })` plots a histogram of the `eruptions` from the Old Faithful Geyser data set `faithful`.

Note:

* The inputted `n_breaks` and `bw_adjust`, are stored within the `input`.  For example, to interactively use `n_breaks`, we need to specify `input$n_breaks`.
* There are curly braces in the `renderPlot({})`
* All possible rendering options are listed in "render functions" on the cheatsheet
* Each type of rendering must be done separately





Publishing Apps
========================================================

To publish your apps: 

* Go to [https://www.shinyapps.io/](https://www.shinyapps.io/) and create a free
account. You can host up to 5 shiny apps. However, you only get limited server
resources dedicated to each user.
* Even better: Use the recently installed Middlebury Shiny Server Pro.





Uploading Files to Middlebury Shiny Server
========================================================

Mac:
* Open Finder
* Menu Bar -> Go > Connect to Server: `cifs://shiny.middlebury.edu/USERNAME`

Windows:

* Open File Explorer
* In address bar, `\\shiny.middlebury.edu\USERNAME`





Uploading Files to Middlebury Shiny Server
========================================================

Once logged in:

* Go into the folder `ShinyApps`
* Create a folder with the name of your Shiny App

For example, I have a folder called `Testing` with a file called `app.R` that
contains the R code for the Shiny App.

The URL for the Shiny App is
* [http://shiny.middlebury.edu/aykim/Testing/](http://shiny.middlebury.edu/aykim/Testing/)
* which auto-redirects to [https://shiny.middlebury.edu:3838/aykim/Testing](https://shiny.middlebury.edu:3838/aykim/Testing)





Today's Exercise: Babynames Shiny App
========================================================

Using `babynames.Rmd`

* Add a menu input option that allows you to specify the color of the smoother
line.
* Add a radio button so that the user has the option can limit consideration to
only one `sex`.

and publish to the Middlebury server under the URL [http://shiny.middlebury.edu/YOUR_MIDD_USERNAME/Babynames/](http://shiny.middlebury.edu/YOUR_MIDD_USERNAME/Babynames/)





Installing Packages
========================================================

For now, I'm investigating if this can be done easier:

* RStudio menu bar -> Tools -> Shell...
* Type `ssh USERNAME@shiny.middlebury.edu`
* Type `R`.
* From R, type `install.packages("ggplot2")` for example
* Select a CRAN mirror in the United States.
* After you've installed all the necessary packages, close the window.



Other Resources 
========================================================

* Slides 
* Check out an online tutorial on the RStudio webpage
[http://shiny.rstudio.com/tutorial/](http://shiny.rstudio.com/tutorial/).

