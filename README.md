## biol-4386-course-project-maddemir

# Analyze Nerve Growth Factor (NGF) deprivation in axonal degeneration
This is for the course BIO:4386 Intro to Scientific Computing in the Spring of 2023. This aims at recreating the graph from the unpublished data behind the NGF Deprivation Experiment(Dr. Daniel Summers Lab)

# Introduction/Background
Alzheimer's disease is one of the most common forms of dementia. It is onset by multiple factors but most commonly seen in loss of neuronal connectivity due to axonal degeneration. One possible mechanism for this loss of axonal connectivity is termed Wallerian degeneration. Wallerian degeneration refers to the location where physical damage is inflicted on an axon and this induces degeneration. Despite physical damage in axons being uncommon, Wallerian degeneration is still very similar to how axons react when undergoing a traumatic injury in the central nervous system. The key point in Wallerian degeneration, is that there is retrograde degeneration of the distal end of an axon that is triggered by the damage site.


![Healthy axons](https://github.com/Intro-Sci-Comp-UIowa/biol-4386-course-project-maddemir/blob/main/healthy%20axons.jpg.jpg)
Image of healthy axons collected on ImageJ, notice the strong thicker axons 

![Unhealthy axons](https://github.com/Intro-Sci-Comp-UIowa/biol-4386-course-project-maddemir/blob/main/sick%20axons.jpg.jpg)
Image of unhealthy azons collected on Imagej, notice the thinning axons breaking down into pieces and thinner colors

 While preparing cell cultures to undergo Wallerian degeneration, first DRG’s are collected from mouse embryos and cultured in Neurobasal Media with added B27, Nerve Growth Factor, and FdU. B27 supports the low to high density growth of short to long term embryonic CNS Neurons. NGF is a neurotrophic protein for the growth, differentiation and survival of sensory dorsal root neurons. FdU removes proliferating cells to obtain pure neuronal cell cultures. After the cells have been cultured for seven days, a physical insult is performed with a razor blade on the axons near the soma. For this study in order to understand NGF’s influence on the neurons death, there are three conditions. First, there is the NGF deprivation condition that is cultured with NGF, washed at DIV7 and then deprived of NGF for 4 hours and then an axotomy is performed. There is a second condition where the cells are cultured with NGF and then washed, NGF is added, and then four hours later an axotomy is performed on the cells. And then there is a third condition where the cells are cultured with NGF, washed and and deprived of NGF for four hours, and then NGF is reintroduced into the cells before performing the axotomy. The intention with this experiment is to see how soon degeneration goes into effect after the axons are cut, and if there is more or less degeneration without NGF.

We can then take images of the cells and run the images through a software that can quantify the amount of degeneration that occurs in the cells using ImageJ. Degeneration indexes under .3 are seen as not undergoing severe degeneration and images quantified at a degeneration index of over .3 are seen as undergoing severe degeneration. In Wallerian Degeneration the production of NGF is upregulated because NGF is necessary for the survival of these neurons. Because NGF is necessary for neuron survival we would expect that with NGF deprivation to see more apoptosis in the neurons of these conditions. We would expect to see a spike in the NGF deprived condition of degeneration in comparison to the not deprived NGF condition.

# Reference
Geden, M. J., & Deshmukh, M. (2016). Axon degeneration: context defines distinct pathways. Current opinion in neurobiology, 39, 108–115. https://doi.org/10.1016/j.conb.2016.05.002  
Reference article in collecting information about NGFs role and how to perform NGF studies 
Daniel Summers, Summers lab
# Expected Figure
The figure I expect to recreate will look like the image below. I plan to document the average amount of axonal degeneration of each condition over how much time has passed since the axotomy. If this becomes too much data for me to work with given the magnitude of images that go into each condition, I will document only the average amount of axonal degeneration of one condition, the NGF deprivation condition. However my goal is to find a method/ or code that I will be able to document many conditions at once. 

![Capture](https://user-images.githubusercontent.com/125223064/218629995-4dce0f9b-8947-448a-9fc0-f76851ed0109.JPG)
Fig. 1 This figure is unpublished and therefore does not have a figure legend yet. However, in my own terms, this figure shows the amount of Axon Degeneration scored on the degeneration index between 0.0-1.0 with scores above 0.3 to be considered undergoing induced/severe degeneration rather than normal cell decay. Along the X- axis is the hour post axotomy of the cells. Three variables are present, the control being the non NGF deprived cell cultures, NGF deprived cultures and NGF that was deprived and later added back to the cells.

# Materials and Methods 
## Data
Dr. Summers has a file with all of the raw images for this experiment before they were run through ImageJ. This is a file with six images per imaging area of the well, there are eight imaging areas in each well and it is done on a 96 well plate. There is also the same data set after it has been run through ImageJ and been quantified in a .csv file.
After the data has been collected onto the .csv file, originally all the data values were separated manually, averaged so that there was one value for each visual field in the well and then found the averages which were then plotted using prism. 

# Analysis
- Our end goal is to find an efficient way of organizing data, and calculating averages of the degeneration index scores in the wells
- To achieve this, I will be taking the raw data from a figure with three variables and focusing on one variable; NGF deprivation, and organizing the NGF deprivation data from the other variables and aim to write a code for ImageJ so that the data will print out sorted onto the .csv file.

