# Dissertationdataerroranalyses
Analysis of the responses when subjects selected a wrong stop type

library(tidyverse)

df_0 <- Inaccuracy_sheet_all

df <- df_0 %>%
  mutate(accuracy_error = "0")

for (ii in 1:nrow(df))
{
  resp <- df$response[ii]
  df$accuracy_error[ii] <- df[ii, resp]
}
df$word= as.character(df$word)
write.csv(df, "solutionB.csv", row.names = FALSE)

