---
layout: post
title:      "How's the weather react/redux style"
date:       2021-04-29 21:50:22 -0400
permalink:  hows_the_weather_react_redux_style
---


Every morning I wake up, and one of the first things I do is open the Weather Channel app on my phone to check the daily forecast so I make sure that my kids are dressed accordingly for school. For my final project of the bootcamp, yes, I said it, FINAL PROJECT, I wanted to create an application that was meaningful and useful to me and my everyday lifestyle. Project builds are more fun if you choose to build something you're passionate about they say, right? So yes, you guessed it, I built my very own current weather application!

The project requirements made it seem like it was going to be smooth sailing...wrong! To say the least, this project has really opened my eyes about just how much we've learned over the last 10 months, and I was so ready to get going on this thing! 

To get it started I used the command create-react-app which gave me access to a lot of different files, including index.js and app.js.  To some, it may be considered backwards, but I started with my frontend work first. With this being my final project of the course I really wanted to make sure it was styled the way I wanted it so I can showcase it on my resume. I got bootstrap going right away and did some really fun styling of a navbar, buttons, links, text, forms, etc. I used an external api from [https://openweathermap.org/current](http://) which made getting my weather info easy and saved me time from manually seeding my database with different cities. The data did come back in kelvin temperature so I found out how to calculate kelvin to Farenheit. 
```
  calFarenheit(temp){
        let faren=Math.floor(((temp - 273.15) * 1.8) + 32)
        return faren
      }
```
Another fun thing I used in my project was a weather icon font that is able to be used with bootstrap which gave me access to icons like the following in my application
 ![](https://camo.githubusercontent.com/91fd4b7a52c88bca80c99267c5189b910fcf176d2067a2917f7b55ccdece3b7d/687474703a2f2f692e696d6775722e636f6d2f586d5a573271332e706e67)
 
 I ended up having 1 container component, also known as the parent to presentational components, and it's titled "WeatherContainer". It's a class component that declares a couple of different dispatch actions, and I'm able render other components inside of it.  It also  holds my api call  and it is connected it to the store.  The store is something new that came with redux, and it's basically a Javascript object that allows components to share state. To declare store in my index.js file  I passed three arguments, the reducer ManageWeather which is where I set default state, thunk middleware, and dev tools extension. my index.js file ended up looking like this:

```
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import manageWeather from './reducers/manageWeather';
import { Provider } from 'react-redux';
import thunk from 'redux-thunk';
import { createStore, applyMiddleware, compose} from 'redux';

const store = createStore(manageWeather, compose(applyMiddleware(thunk), window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__()));

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
document.getElementById('root')
);
```
 
 With having the basics set up and styling taken care of,  a requirement of needing  5 stateless components, I was worried it was going to be hard to get 5, however they quickly add up! I'm really happy with the way everything came together on the frontend of my application.

As far as the backend goes, we were required to use a rails api backend which took me back to writing some ruby code. That seemed to have been a lifetime since I had been outside of javascript!! I used a rails model generator  and the command rails new to get my backend file structure set up. I kept the backend of my project very simple. So simple in fact that I only had one model! Yep, no relationships between models and it helped keep my code nice and clean.  I have a "favorite" model which has one single attribute of location. My schema looked like the following:

```
ActiveRecord::Schema.define(version: 2021_04_27_163337) do

  create_table "favorites", force: :cascade do |t|
    t.string "location"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
  end

end
```

To finish up my project I was tasked with doing a GET and POST fetch to persist something of my choice to the database in my backend. I chose to use a favorite object and the fetch calls were handled inside of an actions folder which is inside of my src folder of my frontend. With all of that being complete I now have a fully functioning Current Weather react-redux application. To say I feel accomplished would be an understatement! Learning react and redux has truly been a journey I won't forget and I'm looking forward to implementing the use of this language into my everyday life as a web developer!


"*There's no such thing as bad weather, just a poor choice of clothing.*" - *Alfred Wainwright*



