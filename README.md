# GSoC 2026 | classbound Evaluation Tasks

> Extending interactive decision boundary exploration for R — one classifier at a time.

This repository documents my complete GSoC 2026 test submissions for the [`classbound`](https://github.com/natydasilva/classbound) package by Natalia da Silva. Each task pushes the package further toward becoming a general-purpose tool for visualizing how classifiers carve up feature space.

---

## What is classbound?

`classbound` is an R package built around a Shiny app (`explorapp()`) that lets you simulate 2D datasets and visually compare how different classification algorithms draw their decision boundaries. Think of it as a live, interactive laboratory for understanding what a classifier is *actually* doing — not just what its accuracy number says.

---

## Task Overview

| Task | What I Built | PR |
|------|-------------|-----|
| Easy | Added RandomForest as a 4th classifier across all panels | [#5](https://github.com/natydasilva/classbound/pull/5) |
| Medium | Grand tour animation comparing rpart vs PPtreeExt on 21D data | — |
| Hard | Brand new Draw-Data panel — draw your own dataset with the mouse | [#4](https://github.com/natydasilva/classbound/pull/4) |

---

## Easy — RandomForest as 4th Classifier

**Location:** [`/easy`](easy/README.md)

The existing app compared 3 methods. I added `RandomForest` as a fourth, updating all three simulation panels (Basic-Sim, SIM-Outliers, MixSim) to display a clean 4-panel boundary comparison side by side.

→ [See implementation + screenshots](easy/README.md)

---

## Medium — Grand Tour Boundary Comparison

**Location:** [`/med`](med/README.md)

Used the `tourr` package to animate random 2D projections of the 21-dimensional `data69_1` waveform dataset, coloring points by predicted class. The resulting GIFs make it immediately obvious why PPtreeExt outperforms rpart — its oblique splits align with the natural geometry of the data, while rparts axis-aligned boundaries miss the structure entirely.

→ [See animated GIFs + analysis](med/README.md)

---

## Hard — Draw-Data Interactive Panel

**Location:** [`/hard`](hard/README.md)

The most open-ended task. I built a brand new `Draw-Data` tab inside `explorapp()` — a blank canvas where you click to place labeled points, then hit Classify to instantly see how Rpart, RandomForest, and PPtreeExt each partition the space you drew. Draw spirals. Draw moons. Draw anything parametric simulation cannot capture.

Robust `tryCatch` handling ensures one failing model never crashes the others.

→ [See screenshots + architecture](hard/README.md)

---

## Run It Yourself
```r
# Install dependencies
devtools::install_github("natydasilva/PPtreeViz")
devtools::install_github("natydasilva/PPtreeExt")
install.packages(c("randomForest", "rpart", "shiny", "ggplot2", "gridExtra", "tourr", "gifski"))

# Launch
devtools::load_all()
explorapp()
```

---

*Submitted by Hargun Kaur | B.Tech ECE (AI Specialization), IGDTUW, Batch 2024–2028*

