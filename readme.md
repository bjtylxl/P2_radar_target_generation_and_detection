# radar_target_generation_and_detection

# Radar Target Generation

One Paragraph of project description goes here

A MATLAB code generate a FMCW waveform and use processing techniques like FFT, 2D FFT and CFAR

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190802103729525.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpYW9fbHhs,size_16,color_FFFFFF,t_70)


![在这里插入图片描述](https://img-blog.csdnimg.cn/2019080210375338.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpYW9fbHhs,size_16,color_FFFFFF,t_70)


![在这里插入图片描述](https://img-blog.csdnimg.cn/20190802103814856.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpYW9fbHhs,size_16,color_FFFFFF,t_70)

# Prerequisites
MATLAB


R = 110; % set DISTANCE OF THE TARGET is 110

v = 30; % set Velocity OF THE TARGET is 30 


# 2D CFAR
The 2d CA-CFAR implementation involves the training cells occupying the cells surround the cell under test with a guard grid in between to prevent the impact of a target signal on the noise estimate.

## STEPS 
1.Determine the number of Training cells for each dimensions. Similarly, pick the number of guard cells.
This number can be picked for try and error. In this project was used, in which gave us a good result.

    * Tr = 10
    * Td = 7 
    * Gr = 5
    * Gd = 3
    * offset = 10.88;

or

    * Tr = 9
    * Td = 5
    * Gr = 5
    * Gd = 3
    * offset = 12;
or 

    * Tr = 80
    * Td = 20 
    * Gr = 7
    * Gd = 7
    * offset =12;

2.Select the grid that includes the training, guard and Cell Under Test (CUT).

3.Measuring the average noise across all the training cells, this gives the threshold.

4.Add a offset to the threshold to keep the false alarm to the minimum. In this project we used 10.88dB.

5.Test the CUT against the threshold, assign a value of 1 if the value is greater, else equate it to zero.

6.Size the CUT are not located at the edges, due the training cells occupying the edges, we suppress the edges to zero.

# Authors

Lily

# License

This project is licensed under the MIT License - see the LICENSE.md file for details

Acknowledgments
Sensor Funsion Nanodegree Program Project