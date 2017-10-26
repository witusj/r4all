---
title       : 1. Data inlezen en beoordelen
description : In dit onderdeel leer je een databron in te lezen en de kwaliteit te beoordelen.
---
## Databron inlezen

```yaml
type: MultipleChoiceExercise
lang: r
xp: 50
skills: 1
key: 58e743fad4
```

gebruik de `read.csv()` functie om data in te lezen vanuit de volgende url:

https://raw.githubusercontent.com/witusj/WorkshopSI/gh-pages/Datasets/sessie%202/subs_data.csv

en te bewaren in een data frame (`myDF`).
Welke `class` heeft de variabele "Jaar"?

`@instructions`
- Character
- Numeric
- Integer
- Factor

`@hint`
Gebruik de `str()` functie.

`@pre_exercise_code`
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer
library(ggplot2)
url <- "https://raw.githubusercontent.com/witusj/WorkshopSI/gh-pages/Datasets/sessie%202/subs_data.csv"
myDF <- read.csv(url)
myDF$Jaar <- as.factor(myDF$Jaar)
p <- ggplot(data = myDF) +
   geom_col(aes(x = Categorie, y = Bedrag, fill = Jaar)) +
   coord_flip()
p
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "Nee, dat is niet correct!"
msg_success <- "Helemaal goed! Als je de functie `str()` toepast op de dataset zie je bij de genoemde variabel de code `int` en dus bevat deze variabele integers (gehele getallen)."
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_bad, msg_success, msg_bad))
```

---
## Gemiddelde berekenen

```yaml
type: NormalExercise
key: f86fc959f9
lang: r
xp: 100
skills: 1
```


`@instructions`
Bereken het gemiddelde van de variabele "Bedrag".

`@hint`
Gebruik de `mean()` functie

`@pre_exercise_code`
```{r}
url <- "https://raw.githubusercontent.com/witusj/WorkshopSI/gh-pages/Datasets/sessie%202/subs_data.csv"
myDF <- read.csv(url)
```

`@sample_code`
```{r}
# Lees data in
url <- "https://raw.githubusercontent.com/witusj/WorkshopSI/gh-pages/Datasets/sessie%202/subs_data.csv"
myDF <- read.csv(url)

# Bereken het gemiddelde van de variabele "Bedrag"

```

`@solution`
```{r}
# Bereken het gemiddelde van de variabele "Bedrag"
mean(myDF$Bedrag)
```

`@sct`
```{r}
test_function_result("mean")
success_msg("Helemaal goed!")
```


---
## More movies

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: a19c8a0264
```

In de vorige oefening hebben we voor één variabele het gemiddelde berekend. Als je dit snel een statistisch overzicht wilt hebben van alle data gebruik je de `summary()` functie.

A dataset with a selection of movies, `movie_selection`, is available in the workspace.

`@instructions`
Gebruik de pas de `summary()` functie toe op myDF

`@hint`
Doe exact wat er gevraagd wordt.

`@pre_exercise_code`
```{r}
url <- "https://raw.githubusercontent.com/witusj/WorkshopSI/gh-pages/Datasets/sessie%202/subs_data.csv"
myDF <- read.csv(url)
```

`@sample_code`
```{r}
# Lees data in
url <- "https://raw.githubusercontent.com/witusj/WorkshopSI/gh-pages/Datasets/sessie%202/subs_data.csv"
myDF <- read.csv(url)

# Gebruik de summary() functie

```

`@solution`
```{r}
# Gebruik de summary() functie
summary(myDF)
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function_result("summary")
success_msg("Good work!")
```
