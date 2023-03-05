# Analyze Nerve Growth Factor (NGF) deprivation in axonal degeneration
This is for the course BIO:4386 Intro to Scientific Computing in the Spring of 2023. This aims at recreating the graph from the unpublished data behind the NGF Deprivation Experiment (Dr. Daniel Summers Lab). 

## Introduction
 Alzheimer's disease is one of the most common forms of dementia. It is onset by multiple factors but most commonly seen in loss of neuronal connectivity due to axonal degeneration. While there are many factors of neurodegeneration, our lab studies the mechanism for loss of axonal connectivity termed Wallerian degeneration. Wallerian degeneration refers to physical damage inflicted on an axon that induces degeneration. This physical damage causes degeneration towards the distal axon terminal unlike retrograde degeneration, where the degeneration is towards the proximal cell body. Despite physical damage in axons being uncommon, Wallerian degeneration is still very similar to how axons react when undergoing a traumatic injury in the central nervous system and an efficient model for our lab. 
 	
![Healthy axons](https://github.com/Intro-Sci-Comp-UIowa/biol-4386-course-project-maddemir/blob/main/healthy%20axons.jpg.jpg)
Image of healthy axons collected on ImageJ, notice the strong thicker axons 

![Unhealthy axons](https://github.com/Intro-Sci-Comp-UIowa/biol-4386-course-project-maddemir/blob/main/sick%20axons.jpg.jpg)
Image of unhealthy azons collected on Imagej, notice the thinning axons breaking down into pieces and thinner colors

Anterograde degeneration is seen in different peripheral neuropathies and diseases and is the cause for diseases such as Alzheimers and/or ALS. For this experiment, our goal is to look at how anterograde degeneration induced by Wallerian degeneration is affected by either having, or not having  supplemental Nerve Growth Factor (NGF) added. NGF is a protein that promotes cell growth, so it is normally added to cells while being cultured to help them survive. To induce the Wallerian Degeneration, the axons are cut just slightly above the soma. This cut is the traumatic injury that the cells will undergo. For this study, we are looking to see if NGF has an influence on neuron cell death or survival during Wallerian Degeneration. Since NGF is a neuron survival factor that we normally add while culturing the cells to promote cell growth, our hypothesis is to see an increase of  regrowth in axons that have started to degenerate from the physical damage.

From there we can take images of the cells and run the images through a protocol that can quantify the amount of degeneration that occurs in the cells using ImageJ. To do this, there is a protocol our lab uses that analyzes the amount of area from the image, and calculates how much of the cell is taking up the area. As the axons die and degenerate, they break down and take up less area in the visual field of the image. The protocol quantifies a number for this, and while not perfect it does provide a quantifiable way of assessing the data rather than a qualitative method. Degeneration indexes under .3 are seen as not undergoing severe degeneration and images quantified at a degeneration index of over .3 are seen as undergoing severe degeneration. In Wallerian Degeneration the production of NGF is upregulated because NGF is necessary for the survival of these neurons. Because NGF is necessary for neuron survival we would expect that with NGF deprivation to see more apoptosis in the neurons of these conditions. We would expect to see a spike in the amount of degeneration in the NGF deprived condition in comparison to the not deprived NGF condition because without the deprivation, the cells are still receiving growth support from the NGF.

![Capture](https://user-images.githubusercontent.com/125223064/218629995-4dce0f9b-8947-448a-9fc0-f76851ed0109.JPG)
Fig. 1 This figure is unpublished and therefore does not have a figure legend yet. However, in my own terms, this figure shows the amount of Axon Degeneration scored on the degeneration index between 0.0-1.0 with scores above 0.3 to be considered undergoing induced/severe degeneration rather than normal cell decay. Along the X- axis is the hour post axotomy of the cells. Three variables are present, the control being the non NGF deprived cell cultures, NGF deprived cultures and NGF that was deprived and later added back to the cells.

This figure really addresses the question behind what can NGF do, as well as what influences axonal degeneration. While it would have been expected that cultured cells deprived of NGF would have higher axonal degeneration (above .3 in the degeneration index) because NGF, a cell growth promoting protein, normally supports cell growth. It was found that the NGF deprivation would in fact lower the amount of axonal degeneration, and slow down the rate of degeneration compared to other groups such as the control group and the NGF addback group.

## Data
Data was given in a .csv file from Dr. Summers. Data for only the NGF addback group is uploaded to github repo with an annotated file explaining how the data will be wrangled to proceed in making the figure.
Access the github repo through the link: https://github.com/Intro-Sci-Comp-UIowa/biol-4386-course-project-maddemir 
Click on the data folder
Click on the DWS 121 NGF addback Bclxl timecourse.csv file
You’ll see the file pull up, and we will focus on the columns listed as filename as well as degeneration index.

## Methods
My end goal with this project is to find an efficient way of organizing data and using data wrangling techniques so that it an be reproducible/usable by others in my lab. I would like to also incorporate calculating the averages of the degeneration index for each well and each hour in the timecourse using all eighth visual fields in each well.
To achieve this, I will be taking the raw data from a figure with three variables and focusing on one variable; NGF addback. My goal is to write a code through R/R studio to take the data after it has been quantified into a .csv file. Through R, I will separate all wells, A10, A11, A12 etc. There are eighth visual fields for each well. In each visual field there is an image taken for hours 1-13. I will take the average of all the images for each hour from all the visual fields. This will give me one summary value for each hour per well made up of the eighth visual fields. After doing this for all wells, I can use these values to graph them.

Ex. 
Well A10

	- Visual field 1
		Images for hours 1-13
	- Visual field 2
		Images for hours 1-13 
	- Visual field 3
		Images for hours 1-13
	- Visual field 4
		Images for hours 1-13
	- Visual field 5
		Images for hours 1-13
	- Visual field 6
		Images for hours 1-13
	- Visual field 7
		Images for hours 1-13 
	- Visual field 8
		Images for hours 1-13 

Average deg index for hour 1 from all 8 visual fields 
Repeat for all 13 hours

## Reflection
 I am unsure if I did the data part correctly/ what was expected, mostly because I didn’t download the data from online. I hope what I did was sufficient and is reproducible but am unsure if I needed to include more info about experiments. I am definitely not confident I am meeting expectations in that section.
	
I am still figuring out how to reproduce the figure, I’ve been working with Yann as well as working on the Coursera course to keep learning how to utilize R in order to learn everything I need to so I can write a code to wrangle the data the way I need to.



