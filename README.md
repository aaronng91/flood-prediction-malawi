# Submission for Flood Prediction in Malawi competition on Zindi

Submission for UNICEF Arm 2030 Vision #1: Flood Prediction in Malawi on Zindi

Link: [https://zindi.africa/competitions/2030-vision-flood-prediction-in-malawi](https://zindi.africa/competitions/2030-vision-flood-prediction-in-malawi)

Obtained **private leaderboard score of 0.1021236** with a **rank of 107**

Final model consists of 3-layer stacked LightGBM, each with hyperparameter values tuned using grid search, with RidgeCV as a final estimator. Besides the original data, additional Land Cover Type data has been added.

## Model Iterations

| Iteration                                                       | Hyperparameters                                                                                | Public Leaderboard |
|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------|--------------------|
| LightGBM                                                        | Default                                                                                        | 0\.14471           |
| LightGBM                                                        | n\_estimator = 50, <br> num\_leaves = 20, <br> max\_depth = 10                                           | 0\.12008           |
| LightGBM <br> \(with normalisation\)                                 | Same as above                                                                                  | 0\.12443           |
| LightGBM <br> \(with 2\-way interactions between all features\)      | Same as above                                                                                  | 0\.29156           |
| LightGBM <br> \(with 2\-way interactions between selected features\) | Same as above                                                                                  | 0\.12317           |
| LightGBM <br> \(with terrain shape data\)                            | Same as above                                                                                  | 0\.13562           |
| LightGBM <br> \(with "no\-rain" data\)                               | Same as above                                                                                  | 0\.12747           |
| 1\-layer stacked LightGBM                                       | Same as above                                                                                  | 0\.10838           |
| 1\-layer stacked LightGBM <br> \(with additional LC data\)           | Same as above                                                                                  | 0\.10510           |
| 2\-layer stacked LightGBM <br> \(with additional LC data\)           | 1st layer: Same as above <br> 2nd layer: <br> n\_estimator = 20, <br> num\_leaves = 2, <br> max\_depth = 2       | 0\.10010           |
| 3\-layer stacked LightGBM <br> \(with additional LC data\)           | 1st & 2nd layer: Same as above <br> 3rd layer: <br> n\_estimator = 25, <br> num\_leaves = 4, <br> max\_depth = 2 | **0\.09747**           |
