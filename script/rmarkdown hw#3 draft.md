require(tidyverse)
df <- read_csv("DWS 121 NGF addback Bclxl timecourse.csv", 
               col_types = cols(), skip = 1) %>% 
  rename(area = "Area analyzed")

df1 <- df %>% 
  separate(filename, into = c('well', 'uuf1', 'uuf2', 'vf', 'marker', 'hour'),
           sep = "_") %>% 
  mutate(hour = str_replace(hour, ".tif", "") %>% as.numeric()) %>% 
  select(well, vf, hour, index = "degeneration index")

df1_mean <- df1 %>%
  filter(vf %in% 1:8, hour >= 1, hour <= 13) %>%
  group_by(well, hour) %>%
  summarize(mean_index = mean(`index`))


print(df1_mean, n = 198)

ggplot(df1_mean, aes(x = hour, y = mean_index)) +
  geom_point(stat = "summary", fun.y = "mean", size = 3, shape = 16) +
  labs(x = "Time (hour)", y = "Degeneration Index", title = "Mean Degeneration Index by Hour")