```r
# Order names by Math score for better visualization
bigclass$name <- factor(bigclass$name, levels = bigclass$name[order(bigclass$Math)])

# Create the bar chart for Math Scores by Name
p_math_name_bar <- ggplot(bigclass, aes(x = name, y = Math, fill = name)) +
  geom_bar(stat = 'identity', color = 'white', alpha = 0.8, show.legend = FALSE) +
  labs(
    title = 'Math Scores by Student Name',
    x = 'Student Name',
    y = 'Math Score'
  ) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, hjust = 0.5),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14, angle = 45, hjust = 1),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = 'white', colour = NA),
    plot.background = element_rect(fill = 'white', colour = NA)
  )

plotly_math_name_bar <- ggplotly(p_math_name_bar)
htmlwidgets::saveWidget(plotly_math_name_bar, file = 'media/plots/math_scores_by_name_bar_chart.html', selfcontained = TRUE)
```
