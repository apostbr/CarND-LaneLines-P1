#**Finding Lane Lines on the Road** 

##Writeup Template

This is my first lesson for the Udacity Self-Driving Car Nanodegree.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

The goal is to apply the computer vision techinques to the sampe, images and videos provided, so the lane lines can be detected and treated accordingly.

It was quite hard to do the initial environment setup, since I recently had to format my machine, and I was quite "rusty" in programming. But I think it all went all at the end.

Actually working with images has proven to be quite straight forward.

Initially, I have applied the same parameters used earlier on the exercices. It worked fine in images. But on the movies, another tratment had to be applied, and I reviewed all the parameters, generating the images accordingly.

In my personal view, I haven´t solved the optional challenge, due to lack of time. But I´ll keep working on it, since I think my setup got quite flexible for that.

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Initially, I have applied all the parameters from the lessons, such as converting the image to grayscale, region masking, canny edge detection, hough transform and the image superposition. 

Then, in order to draw a single line I have modified the draw_lines functions. What I did was to follow project suggestions. Initially, I took each segment from the Hough line selection, and took the average point from each of the lines. Then I created multiple larger segments of lines, by selecting the the ones in the right lane, and the ones in the left lane from their slope. Separating it in two different lists (ptsr and ptsl). By parsing these lists, the program had the lines from left and right lanes separated for use.


###2. Identify potential shortcomings with your current pipeline

I have chosen this pipeline, because I think it would work better with curved roads than the single line strategy. If required, I can work on another segment reduction, to make a single line. This is quite ready in the project.

One potential shortcoming would be what would happen when there is too many interference in the images, the solution gets a bit lost. I would rather evolve the solution to make more data visible.

This sort of decision may impact on different environments, such as clear weather conditions, or even reduced visibility, since, it is one fixed point in the screen.

###3. Suggest possible improvements to your pipeline

A possible improvement would be to refine the slope parameters to fetch only real lanes, for the additional challenge. Also, I would like to work more in the draw_lines function, to make it more complex and covering the lane detection with more precision.

Another potential improvement could be to reduce the amount of segments, to another averages, reducing the impact of the interferences in the region within the polygon.
