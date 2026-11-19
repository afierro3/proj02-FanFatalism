# Project 02 Proposal: Quantifying Fan Fatalism

**Team members:** Tony Fierro

See the [Project 02 instructions](https://data385.github.io/project/proj02_wholegame.html) for what goes in each section. Bullet points are great. Put any images in an `img/` folder.


## 1. Problem statement

Is team-level injury variance in the National Football League driven by random distribution (luck), or are there statistically significant structural factors that make certain franchises consistently more injury-prone?


## 2. Research question

Do certain NFL teams consistently report more player injuries than other teams, or is the variation in reported injuries primarily due to random chance?

**Response variable:** Number of reported player injuries per team per season.

**Explanatory variables:** NFL team and season (year).

**Goal:** Compare reported injury counts across NFL teams over multiple seasons to determine whether certain teams consistently experience above-average injury levels.


## 3. Data acquisition

I plan to use historical NFL injury report data from the nflverse project, accessed through the `nflreadr` package in RStudio. The dataset contains player-level injury reports, including NFL teams, seasons, weeks, and injury-related statuses. I will use this information to compare reported injuries across teams and determine whether certain franchises consistently experience higher injury levels.

### a. Confirm viability

I will download historical NFL injury report data using the `nflreadr` R package, part of the open-source nflverse project. The data originate from publicly available NFL injury reports and are distributed through nflverse for statistical analysis. I successfully imported the 2024 season into RStudio, confirming that the dataset contains 6,215 observations and 16 variables.

**Data source:** [nflreadr — Load Injury Reports](https://nflreadr.nflverse.com/reference/load_injuries.html)

### b. Variables of interest

The following variables from the NFL injury dataset will be used to analyze injury patterns across teams and seasons:

- `season` (integer): The NFL season year, used to compare injury trends over time.
- `team` (character): The NFL team's abbreviation, used to compare injuries between franchises.
- `week` (integer): The week of the NFL season when the injury was reported.
- `gsis_id` (character): Unique player identifier, used to distinguish players and avoid duplicate counts within the same week.
- `report_primary_injury` (character): The primary injury listed on the player's game injury report.
- `report_status` (character): The player's game status, such as Out, Questionable, or Doubtful.
- `practice_primary_injury` (character): The injury or reason listed on the player's practice report, used to identify and exclude non-injury-related absences.
- `position` (character): The player's position, used to explore whether injury patterns differ by position.

## 4. Data example

I successfully imported the 2024 NFL injury dataset using `nflreadr` in RStudio. The dataset contains 6,215 observations and 16 variables, including team, season, week, player position, injury type, and injury status.

[View NFL Injury Data Example](data_management.pdf)

## 5. EDA

I will use `nflreadr::load_injuries()` to import historical NFL injury reports and `dplyr` functions such as `filter()`, `group_by()`, and `summarise()` to clean and organize the data by team and season. I will exclude non-injury-related reports and account for players appearing multiple times in the dataset.

I will use `ggplot2` to create bar charts comparing reported injuries across NFL teams and line graphs showing injury trends over multiple seasons. Summary statistics, including averages and standard deviations, will help identify teams that consistently report more injuries than the league average.


## 6. Modeling

I plan to use linear regression to examine the relationship between NFL teams and reported injury counts across multiple seasons.

- **Response variable:** Number of reported player injuries per team per season.
- **Explanatory variables:** NFL team (categorical) and season (numeric).
- **Model:** Use `lm()` in R to compare injury counts across teams and examine whether injury levels change over time.

I will also use bootstrapping to calculate confidence intervals for differences between team injury averages and the league average. This will help determine whether certain teams consistently experience higher reported injury counts or whether the observed differences could be explained by random variation.

## 7. Communicate

I plan to present my findings using a combination of a slide presentation and a poster display. I will use bar charts to compare injury counts across NFL teams and line graphs to illustrate trends over multiple seasons. The presentation will focus on answering the question, "Is My Team Cursed?" by explaining whether the data suggest that certain teams consistently experience more injuries than others. I will keep the visualizations and statistical explanations simple enough for both NFL fans and people unfamiliar with football to understand.

## 8. LLM disclaimer

I plan to use AI to assist with the graphical design and layout of my final presentation and poster. I will independently review and verify AI-generated suggestions, perform the statistical analysis in RStudio, and ensure that my conclusions are supported by the data. I will use publicly available NFL injury data and will not share private or sensitive information with AI tools.

