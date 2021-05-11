---
layout: post
title:      "React's setState()"
date:       2021-05-11 15:21:59 -0400
permalink:  reacts_setstate
---


The time had finally come for me to do my final assessment! While I was extremely nervous and excited, it had become clear to me during the time I had spent with my assessor that I needed a refresher on a function that comes with react, setState(). So here I am, writing a blog on it that not only helped me gain a deeper understanding of what it is and what it does, but will hopefully be useful to somebody else. The following questions are some that I asked for myself and that you may also may find yourself wondering.

What is this.setState()?
-setState() is a function that is available to all React components that use state.

What does it do?
-it allows us to let React know that the component state has changed.

Why is it important?
-it is important because it allows us to dynamically change state within a component. When setState() is used, the component is automatically re-rendered with whatever we have setState() set to.

What lifecycle methods is it acceptable to use setState()
-setState() is useful in some, but not all of reacts lifecycle methods. It is able to be used in componentWillMount, componentDidMount, componentWillReceiveProps(), and shouldComponentUpdate().

But why can't I use it in all lifecycle methods?
-when setState() is used like previously mentioned, it causes the component it's being called in to re-render, so by using it in certain lifecycle methods it could trigger a re-render again which will lead to an infinite loop and break your application. 

So what lifecycle methods should I avoid calling setState() in?
-setState() should be avoided in the following lifecycle methods to avoid an infinite loop; componentWillUpdate and componentDidUpdate. It should also be avoided in the render() method because although we have access to both state and props in the render() method, we aren't able to modify it directly here, thus resulting in an infinite loop again if called here.

Below is an example of how I used setState() within a component in my react-redux project that I built for my final project of Flatiron's bootcamp. It's a weather application where a user is able to get the current weather for a location they enter, and set that location as a favorite if they wish. For my live coding portion I was asked to build a feature that allows a user to then set one of those favorite locations as a "home" weather location using a toggle. It was a temporary feature so it didnt persist to the back end of my project.

```
import {Link} from 'react-router-dom'
import React, { Component } from 'react';

class Favorite extends Component {
    constructor() {
        super()
        this.state=({
            favorite: false
        })

    }

    handletoggle = () => {
        this.setState({
            favorite: !this.state.favorite
        })
    }

    render() {
        return (
           
            <div className="container">
                <div className="card ">
                    <button onClick={()=> this.props.getWeather(this.props.location)}>
                        <Link to='/favorite-weather'>{this.props.location}</Link>
                    </button>
                    <button onClick={()=> this.handletoggle()}>
                        {this.state.favorite ? "home" : "make home"}
                    </button>
                </div>
        </div>
        );
    }
}
```

First, I set inital state in a constructor method of favorite to be false, as I chose to tackle this by using a boolean value for initial statem, and a ternary operator to complete the asignment. I built a handletoggle arrow function that calls, you guessed it, this.setState() and inside of that I'm saying that I want to take whatever state is and set it to favorite: !this.state.favorite, thus changing the value of the current state to the opposite value of what it currently is. In the render method is where I created a button that had the word "make home" on it initiallym and it's is saying, upon clicking this button, we call this.handletoggle which triggers the value of our state to change from true to false and returning the ternary operator which is asking, IF this.state.favorite true ? the text on the button will render "home" ELSE the button will read "make home"  In the example I'm using the "this" keyword because I'm using a class component and it's referring to an instance of the favorite class.

Going back to review this topic has been beneficial to me. I hope it also helps another student in their understanding of the concept.

