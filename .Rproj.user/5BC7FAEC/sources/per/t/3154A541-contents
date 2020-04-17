library(ggplot2)
library(GetTDData)


df.yield <- get.yield.curve()  
my.df <- df.yield$type$real_return
str(df.yield)

p <- ggplot(df.yield, aes(x=ref.date, y = value) ) +
  geom_line(size=1) + geom_point() + facet_grid(~type, scales = 'free') + 
  scale_x_date(date_breaks = "6 months", date_minor_breaks = "3 months", date_labels = "'%y") +
  scale_y_continuous(n.breaks = 20) +
  labs(title = paste0('The current Brazilian Yield Curve '),
       subtitle = paste0('Date: ', df.yield$current.date[1]))     

print(p)  



# plot data (yields)
p <- ggplot(data = my.df, aes(x = as.Date(ref.date), y = yield.bid, color = asset.code))
p <- p + geom_line() + scale_x_date() + labs(title = '', x = 'Dates', y = 'Yields' )
print(p)

