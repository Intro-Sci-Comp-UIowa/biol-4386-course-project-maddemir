# So first i’m getting everything set up, so im making sure I have the package I need, and I am importing the data into a tibble, skipping the first line of the csv file so that it would be tidy, as well as renaming one of the columns.
require(tidyverse)
df <- read_csv("DWS 121 NGF addback Bclxl timecourse.csv", 
               col_types = cols(), skip = 1) %>% 
  rename(area = "Area analyzed")

#Next up, its time to tidy up the data some more, here I am separating one column into multiple different columns, creating new columns, and modifying the contents of the set for the columns that I am interested in.
df1 <- df %>% 
  separate(filename, into = c('well', 'uuf1', 'uuf2', 'vf', 'marker', 'hour'),
           sep = "_") %>% 
  mutate(hour = str_replace(hour, ".tif", "") %>% as.numeric()) %>% 
  select(well, vf, hour, index = "degeneration index")
# Next I am creating a new array with the contents I am interested in. This means I am looking at visual fields 1-8, and looking for hours 1-13. I am grouping this content by both the well and the hour. I am then finding the mean of the degeneration index for all eight visual fields of each hour for each well. I’m setting this to generate all the means for the entire data sheet.
df1_mean <- df1 %>%
  filter(vf %in% 1:8, hour >= 1, hour <= 13) %>%
  group_by(well, hour) %>%
  summarize(mean_index = mean(`index`))
print(df1_mean, n = 198)
# Last up is to create a scatter plot with all these means, so that it is averaging all the wells and plotting the degeneration index by hours 1-13 on the x-axis.
ggplot(df1_mean, aes(x = hour, y = mean_index)) +
  geom_point(stat = "summary", fun.y = "mean", size = 3, shape = 16) +
  labs(x = "Time (hour)", y = "Degeneration Index", title = "Mean Degeneration Index by Hour") 
