---
title: 'Chapter Title Here'
description: 'Chapter description goes here.'
free_preview: true
---

## Formatting strings

```yaml
type: VideoExercise
key: 6b700ef407
xp: 50
```

`@projector_key`
b830b2075b68dfb75dfcbf2e59156135

---

## Example coding exercise

```yaml
type: NormalExercise
key: 2bafef99a3
lang: r
xp: 100
skills: 1
```

This is an example exercise.

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Insert exercise title here

```yaml
type: NormalExercise
key: 01bd99578e
xp: 100
```

Construct a regular expression to pool out the age, type of time measurement and the gender from the dataset and then to convert your results to data frame.
For installing the package from git hub repository you can use function  [install_github()] (https://www.rdocumentation.org/packages/devtools/versions/1.12.0/topics/install_github) developed by Hadley Wickham for install a package directly from GitHub, with ability to install multiple packages. The installation of GitHub package > has been done for you. The text description can help you to construct the regular expression for pattern
Create pattern to capture "()" 
one optional digit "[\d]?" and one digit 
"[\d]",
then optional space "[\s]?" 
then capture "()" unit YO or YR or MO as non capturing group "(?:YO|YR|MO)" 
then again optional space "[/s]?" and 
capture "()" gender M or F "(?:M|F)" as non capturing group "(?:)"
do not forget to escape \ in regex string.

`@instructions`
- Load > neiss package into the working environment, and check

`@hint`
Use rebus functions to get regular expression for pattern
```
patternRebus <- capture(optional(DGT) %R% DGT) %R%  
        optional(SPC) %R% capture(or("YO", "YR", "MO")) %R%
        optional(SPC) %R% capture(or("M", "F"))
```

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Load nisse library
library(_____)

# inspect neiss::injuries
str(____)

# Extract narrative column from neiss::injuries: narr
____ <- neiss::injuries_____

# Create pattern with Rebus package (optional for help reasons)
patternRebus <- capture(optional(DGT) %R% DGT) %R%  
        optional(SPC) %R% capture(or("YO", "YR", "MO")) %R%
        optional(SPC) %R% capture(or("M", "F"))

# Create regular expression, to capture age, unit and group: RegExPatt
pattern <- "([\\d]?\\d)[\\s]?((?:YO|YR|MO))[\\s]?((?:M|F))"

# Convert age, unit and gender, from narr to dataframe with stringr match function: DF_narr 
DF_narr <- as.data.frame(str_match(narr, pattern = pattern)[,2:4])

#Name the columns of DF_narr  
colnames(DF_narr) <- c("Age", "Unit", "Gender")
```

`@solution`
```{r}

```

`@sct`
```{r}

```
