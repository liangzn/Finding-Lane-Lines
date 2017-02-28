**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Get familiar with Python (First time to use Python)

---

Reflection

1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used cv2.Canny funtion to filter off edges in the grayscale copy. Then I picked edges in a four sided polygon area. Then I separate all edge points into left and right group, corresponding to the left line and right line. Then I used polyfit funtion to draw a straight line to between most of all points in each group, as the simulation of line of each side.

2. Identify potential shortcomings with your current pipeline

The funtion to separate all edge points into left and right group might be not reliable enough when the car turns.

Currently it cannot draw curve lines when the car turns.

3. Suggest possible improvements to your pipeline

It's possible to add a verification (like slope detecting) to check whether the output lines (drawn lines) are overlapped with most of original edge lines. If not, might need to remove some remote points and then redraw lines.