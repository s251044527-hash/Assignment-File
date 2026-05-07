```r
p_math_hist <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 50, fill = '#0072B2', color = 'white', alpha = 0.8) +
  labs(
    title = 'Distribution of Math Scores',
    x = 'Math Score',
    y = 'Frequency'
  ) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, hjust = 0.5),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = 'white', colour = NA),
    plot.background = element_rect(fill = 'white', colour = NA)
  )
plotly_math_hist <- ggplotly(p_math_hist)
htmlwidgets::saveWidget(plotly_math_hist, file = 'media/plots/math_scores_histogram.html', selfcontained = TRUE)
```
