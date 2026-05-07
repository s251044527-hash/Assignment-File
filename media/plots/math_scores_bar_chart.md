```r
p_math_bar <- ggplot(bigclass, aes(x = factor(Math))) +
  geom_bar(fill = '#0072B2', color = 'white', alpha = 0.8) +
  labs(
    title = 'Distribution of Math Scores (Bar Chart)',
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
plotly_math_bar <- ggplotly(p_math_bar)
htmlwidgets::saveWidget(plotly_math_bar, file = 'media/plots/math_scores_bar_chart.html', selfcontained = TRUE)
```
