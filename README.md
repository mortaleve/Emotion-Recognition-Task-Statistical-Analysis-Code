Emotion Recognition Task – Data Analysis Code

This repository contains the complete R code used to process, analyze, and visualize the data reported in the associated manuscript on emotional recognition performance in university students.

The analyses focus on accuracy and reaction time in a dynamic facial emotion recognition task, using mixed-effects modeling and robust descriptive procedures.

⸻

Overview

The analytical workflow includes:
	•	Data preparation and merging of experimental task data with PANAS questionnaire scores
	•	Psychometric analysis of the PANAS scale (Cronbach’s alpha)
	•	Descriptive analyses of accuracy and reaction time by emotion and academic group
	•	Mixed-effects logistic regression models for accuracy at the trial level
	•	Linear mixed-effects models for log-transformed reaction time
	•	Post hoc comparisons based on estimated marginal means
	•	Visualization of predicted probabilities and reaction times with BCa bootstrap confidence intervals

All analyses were conducted in R following reproducible research principles.

⸻

Data Structure

The analyses rely on the following datasets:
	•	trials_master: Trial-level data from the emotion recognition task, including:
	•	participant identifier
	•	target emotion
	•	response accuracy (binary)
	•	reaction time (ms)
	•	panas_master: Item-level PANAS responses, including:
	•	participant identifier
	•	PANAS item
	•	response value
	•	demographic variables (age, gender, academic group)

These datasets are merged into a unified trial-level dataset (trials_mixed) used for inferential modeling.

⸻

Statistical Analyses

Accuracy
	•	Accuracy was analyzed at the trial level using generalized linear mixed-effects models with a binomial (logit) link.
	•	Fixed effects included target emotion, academic group (first vs. fourth year), age, gender, positive affect (PA), and negative affect (NA).
	•	Random intercepts were specified for participants to account for within-subject dependence.
	•	When the interaction between emotion and academic group was significant, post hoc comparisons were conducted separately by group using odds ratios with Holm correction.

Reaction Time
	•	Reaction time analyses were restricted to correct trials.
	•	Reaction times were log-transformed to address positive skewness.
	•	Linear mixed-effects models were fitted with the same fixed and random effects structure as the accuracy models.
	•	Interaction effects between emotion and academic group were tested via model comparison.
	•	Post hoc comparisons between emotions were conducted using estimated marginal means with Holm-adjusted p-values.

⸻

Bootstrap Confidence Intervals

Descriptive figures for accuracy and reaction time include bias-corrected and accelerated (BCa) bootstrap confidence intervals, computed at the participant level to respect the repeated-measures structure of the data.

Bootstrap procedures were implemented using the boot package with 2,000 resamples.

⸻

Software and Packages

Analyses were conducted in R using the following main packages:
	•	lme4 – mixed-effects modeling
	•	emmeans – estimated marginal means and post hoc contrasts
	•	boot – BCa bootstrap confidence intervals
	•	ggplot2 – data visualization
	•	dplyr, tidyr, stringr – data manipulation

⸻

Reproducibility

All code is organized sequentially and annotated to allow full reproducibility of the analyses reported in the manuscript, from raw data preparation to final statistical models and figures.

⸻

Author

Luciano Silva Aguayo
Doctoral Program in Education
University of Concepción, Chile
