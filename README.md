# classbound: GSoC 2026 Evaluation Tasks

Welcome to my submission for the Google Summer of Code (GSoC) 2026 evaluation tasks for the `classbound` package!

This repository contains my solutions for the Easy, Medium, and Hard tasks designed to extend the classifier boundary exploration capabilities of the package.

## Easy Task: RandomForest Classifier Integration

PR Link: [natydasilva/classbound#5](https://github.com/natydasilva/classbound/pull/5) Location: `/easy`

Summary: Integrated RandomForest as a 4th classification method into the `explorapp()` Shiny application. The app now displays a 4-panel split comparing `rpart`, `PPtree`, `PPtreeExt`, and `RandomForest` boundaries across all three simulated datasets (Basic-Sim, MixSim, and SIM-Outliers).

For screenshots and detailed implementation notes, see the [Easy Task README](easy/README.md).

## Medium Task: Grand Tour Boundary Comparison

Location: `/med`

Summary: Reproduced Figure 11 from the Enhanced Projection Pursuit Tree Classifier paper. Used the `tourr` package grand tour on the 21-dimensional `data69_1` dataset to compare how `rpart` (axis-aligned splits) and `PPtreeExt` (oblique splits) partition the data space.

For the generated animated GIFs, static visual comparisons, and reproducible scripts, see the [Medium Task README](med/README.md).

## Hard Task: Interactive Draw-Data Exploration

PR Link: [natydasilva/classbound#4](https://github.com/natydasilva/classbound/pull/4) Location: `/hard`

Summary: Added a completely new, interactive "Draw-Data" tabset panel to the `explorapp()` Shiny UI. Users can now draw custom 2D point clouds using their mouse (e.g., spirals, moons), assign classes on the fly, and dynamically evaluate the decision boundaries of all integrated classifiers. Includes robust error handling (`tryCatch`) to safely fail when models receive degenerate hand-drawn data.

For screenshots and UI/Server architecture details, see the [Hard Task README](hard/README.md).

## How to Test the Shiny App Locally

To test the Easy and Hard tasks (which modify the `explorapp` interface), you will need the relevant branches checked out.

1. Ensure prerequisites are installed:
```r
install.packages(c("randomForest", "gridExtra", "ggplot2", "shiny", "tourr", "rpart", "gifski"))
devtools::install_github("natydasilva/PPtreeViz")
devtools::install_github("natydasilva/PPtreeExt")
```

2. Load the package and launch the app:
```r
devtools::load_all()
explorapp()
```

Thank you to the mentors for reviewing my submission!

