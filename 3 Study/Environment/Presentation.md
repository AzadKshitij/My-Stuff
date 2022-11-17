---
dasdadasdasd
---

---
	Hello Everyone this is group 18 presentintation on predicting Wind and solar generation from werather data.  

---
Agenda for the presentation is...

Mehodology we used to solve the problem

Challenges we faced in our path.

Application of our solution

What we get as a Result.

And finally

the conclusion.

---

- As wind and solar power is becoming more and more widespread the need of predicting the future is becoming more to get the best result out of it.
- The future of power scheduling heavily depends on accurate forecasting of solar and wind power generation. 
- Generally we can not relay on the renewable energy source for near future because the are dispersive. Using the prediction model we can solidify the future generation and reduce the use  of fossil fuels. 
- We re predicting the future wind and solar power generation from  the data gathered over the years containing weather information and power generation to build and train the model.  
---
We used mentioned parameters for wind and solar generation from the dataset. 


For Solar Energy:

- Total top-of-the atmosphere horizontal radiation.
- Total ground horizontal radiation.
- temperature at 2 meter above the displacement height.

For wind we used:

- Velocity at displacement point above height h1 and h2.
- displacement height above 2 meter from ground.
- displacement height above 10 meter from ground.
- roughness length
- Air density at surface
- Air pressure at surface.

---

Now methods for Solar generation. 
We used Linear regression model to train the data on.

1. We first sampled the data into chuncks 
2. feed that data into the linear regression model.
3. We did many iteration and by using the method of cross validation we the best performing dataset and Linear  regression model trained on it.
4. To predict the solar generation we we get test data containing parameters mentioned in the last slide. feed it to the regression model and get the amount of solar energy that can be generated from the given input. 
5. Here is the pseudo code for the same.

---
Now methods for Wind generation. 

We did pretty much the same thing to solve this problem as well as the plot of the data we will se in the upcoming slides was very similar in fashion. 

---

Now Nikhil will continue from here

