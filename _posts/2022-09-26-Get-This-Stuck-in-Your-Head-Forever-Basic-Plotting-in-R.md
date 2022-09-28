---
layout: post
title:  "Get This Stuck in Your Head Forever: Basic Plotting in R"
date:   2022-09-26
author: Jackson Switzer
description: Explaining the basics of how to make plots in R (and encouraging you to change the way you think about learning programming)
headline: Idk what the headline is but maybe it's this?
image: /assets/images/titlepicattempt3.png
---

## The Why

I was three years into my statistics degree when I decided it was finally time: I was going to stop copying and pasting code every time I wanted to make a plot in R.

No more “How do I format the input, again?”

No more “What does this code mean, again?”

It was time to buckle down and give the basics some attention—some real attention—and remember the code itself, rather than remembering what website explains how to do it.

My hope is that you only read this blog post once; think about it deeply as you read, do some practice as you go, and solidify it in your memory forever. In fact, that’s what this post is really about, far more than it’s about plotting: you shouldn’t rely on the internet, no matter how often people tell you “a programmer’s biggest skill is knowing how to Google!” You need to understand, really understand, fundamental programming skills, and your repertoire of things you can do without looking anything up needs to be constantly growing. Otherwise, you’ll become resentful of your education or your work, feeling you’re truly not learning anything. Your impostor syndrome will grow…and grow…and grow.

Today we’ll discuss just one of those core skills, one you should be able to do while wrapped in a blanket, sitting by the fire in your cozy, off-the-grid mountain cabin: plotting. Data visualization is a core skill for any data scientist. Humans’ brains process visual information more quickly and intuitively than text, so clear communication of your results will almost always involve some kind of visual—a plot or a graphic. These visuals will also be useful for you in all phases of your work. For example, you may want to use plots to help you better understand your input data, to compare the metrics of machine learning models, or to see the spread around regression lines, among countless other things.

None of these data visualizations need be complex, and understanding the fundamentals of plotting in R will enable you to quickly and confidently create simple visualizations as you work. It is also a necessary building block for learning to visualize data in more complex ways.

## Basic Plotting in R

One of the first things you’ll want to know how to do is plot a set of x and y coordinates on the Cartesian plane. For this, use the function plot(x,y). x and y should be vectors of the same length. The first index of the vectors x and y are the x and y coordinates of the first point to be plotted, the second index of the vectors x and y are the x and y coordinates of the second point to be plotted, and so on.

Alternatively, you may omit y, if you pass into x a structure with its own “plot” method, such as a table, tibble, or data frame.

By default, each point is shown as a hollow circle. The style of the plot can be changed by adding a third parameter, “style,” to plot(). For instance, if instead of the hollow circles you would like vertical lines from the x-axis to the points, you would type `plot(x=your_x_vector, y=your_y_vector, style=‘h’)`. For all the style options, see [the documentation](https://www.rdocumentation.org/packages/graphics/versions/3.6.2/topics/plot).

You may also label the plot with a title, text below the plot, x-axis label, and y-axis label, by passing strings into the parameters “main”, “sub”, “xlab”, and “ylab”, respectively.

There are many other available adjustments, including changing the shape (parameter: pch), size (cex), and color (col) of points. (For more details, [this](https://r-coder.com/plot-r/) website is a good reference; see the “R plot pch” section.)

### Code Examples

Here are a few examples (practice on your own, too)

`my_x` is the vector `c(1,2,3,4,6)`, and `my_y` is `c(2,4,6,20,6)`

`plot(my_x, my_y)` yields the following:

![First plot](https://raw.githubusercontent.com/jacksonswitzer/stat386-projects/main/assets/images/post1pic1.jpeg)

`plot(my_x, my_y, pch=11, cex=3, col='lightgreen', main='Example Plot', sub='(with fun shapes and colors)', xlab="Jackson's x-values", ylab="Jackson's y-values")` looks like this:

![Second plot](https://raw.githubusercontent.com/jacksonswitzer/stat386-projects/main/assets/images/post1pic2.jpeg)

## Color-coding by a Variable

Another useful ability is coloring the points according to the value of a specified variable. This lets you see relationships that would otherwise disappear into a slew of points. To do this, pass a vector of color names (see [this website](http://www.sthda.com/english/wiki/colors-in-r) for a list of the available colors) into the “col” parameter, followed by the name of the variable you want to color by in square brackets.

### Another Code Example

Example:

First, we’ll declare three variables

`number <- c(1,2,3,4,6)`

`doubled <- c(2,4,6,8,12)`

`even <- factor(c(F,T,F,T,T), levels=c(T,F))`

Then I’ll put them into a data frame with three columns

`my_df <- data.frame(number, doubled, even)`

We declared `even` as a factor because it lets us explicitly control the order in which R will color-code the points. We’ll do this in the next step.

Now, plot the data. As before, one vector will provide x-values and another will provide y-values. But this time, we’ll use the third to color-code based on whether the x-value is even or odd. Notice that the first color, black, is used for the first factor level, True, and the second color, red, is used for the second factor level, False.

`plot(my_df$number, my_df$doubled, pch=19, cex=2, col=c('black','red')[my_df$even])`

![Third plot](https://raw.githubusercontent.com/jacksonswitzer/stat386-projects/main/assets/images/post1pic3.jpeg)

## Conclusion

We’ll stop here for today, but don’t leave yet!

Pause.

Take a breath.

Review what you’ve read. Have you learned it—really learned—or is it just hovering at the surface of your mind, ready to disappear once you move on from your current task?

Learn well, learn deeply, then never look it up again. You’re not an impostor; you’re more than a monkey trained to flee to Google every step of the way. You’re a data scientist.

This attitude and approach to learning coding has helped me be more confident and competent—have you experienced anything similar? Or do you disagree? (I wouldn’t want to encourage people to do something that could end up hurting them!) Let me know your thoughts in the comments.
