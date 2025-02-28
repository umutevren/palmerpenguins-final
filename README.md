# Palmer Penguins MLOps Project

![MLOps Cycle](https://vetiver.rstudio.com/images/ml_ops_cycle.png)

## Overview

This project demonstrates a complete MLOps pipeline in R, using the Palmer Penguins dataset to predict penguin sex based on various physical measurements. It showcases modern machine learning operations practices including model development, hyperparameter tuning, versioning, and deployment.

## Features

- **Data Analysis**: Uses the `palmerpenguins` dataset with comprehensive EDA
- **Model Development**: Implements multiple models including:
  - Logistic Regression
  - Random Forest (using `ranger`)
  - Neural Networks (using `torch` via `brulee`)
- **MLOps Best Practices**:
  - Hyperparameter tuning with Bayesian optimization
  - Model versioning with `vetiver`
  - Model deployment via API using `plumber`
  - Resource sharing across sessions with `pins`

## Project Structure

- `the-whole-game.qmd`: Main project notebook showing the complete MLOps workflow
- `hyperparameter-tuning.qmd`: Detailed exploration of model tuning techniques
- `plumber.R`: API endpoint definitions for model deployment
- `Dockerfile`: Container configuration for deployment
- `pins-r/`: Directory containing pinned models and resources

## Dependencies

Main R packages required:
```r
library(tidyverse)         # data wrangling and cleaning
library(tidymodels)        # modeling and machine learning
library(palmerpenguins)    # penguin dataset
library(ranger)            # random forest model engine
library(brulee)            # neural network with torch
library(pins)              # sharing resources across sessions & users
library(vetiver)           # model versioning and deployment
library(plumber)           # API creation
```

## Getting Started

1. Clone this repository
2. Install the required R packages:
   ```r
   install.packages(c("tidyverse", "tidymodels", "palmerpenguins", "ranger", 
                     "brulee", "pins", "vetiver", "plumber"))
   ```
3. Open the `r-mlops.Rproj` file in RStudio
4. Run the `the-whole-game.qmd` notebook to see the complete workflow

## Model Deployment

The project includes a Dockerfile for containerized deployment. To deploy:

1. Build the Docker image:
   ```bash
   docker build -t palmer-penguins-mlops .
   ```
2. Run the container:
   ```bash
   docker run -p 8000:8000 palmer-penguins-mlops
   ```

The model API will be available at `http://localhost:8000`

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- The Palmer Penguins dataset by Dr. Kristen Gorman and the Palmer Station, Antarctica LTER
- The `vetiver` team for their MLOps framework
- The `tidymodels` team for their comprehensive machine learning toolkit 