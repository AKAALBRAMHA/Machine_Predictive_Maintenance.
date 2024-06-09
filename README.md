# Predictive Maintenance using Synthetic Dataset

In industrial settings, predictive maintenance is crucial for preventing unexpected equipment failures and optimizing maintenance schedules. This project aims to develop a predictive model to accurately identify machine failures using a synthetic dataset that closely mimics real-world industrial maintenance data.

## Dataset Description

The synthetic dataset consists of 10,000 data points, each represented by 14 features. The features are designed to reflect real-world industrial maintenance data. Here is a description of each feature:

- **UID**: A unique identifier ranging from 1 to 10,000.
- **productID**: A combination of a letter (L, M, or H) indicating product quality (Low, Medium, High) and a variant-specific serial number.
  - L: Low quality (50% of products)
  - M: Medium quality (30% of products)
  - H: High quality (20% of products)
- **air temperature [K]**: Generated using a random walk process, normalized to a standard deviation of 2 K around 300 K.
- **process temperature [K]**: Derived from the air temperature with an additional 10 K and normalized to a standard deviation of 1 K.
- **rotational speed [rpm]**: Calculated based on a power of 2860 W, overlaid with normally distributed noise.
- **torque [Nm]**: Normally distributed around 40 Nm with a standard deviation of 10 Nm, ensuring no negative values.
- **tool wear [min]**: Varies with product quality, adding 5 minutes for high quality (H), 3 minutes for medium quality (M), and 2 minutes for low quality (L).
- **machine failure**: Indicates whether the machine has failed at the given data point. This is the primary target variable.
- **failure type**: Specifies the type of failure if a machine failure has occurred. This should not be used as a feature to avoid data leakage.

## Objectives

The primary objective is to develop a predictive model that can accurately identify whether a machine will fail (machine failure) based on the provided features. A secondary objective is to classify the type of failure when a failure occurs.

## Methodology

1. **Data Balancing**: Applied SMOTETomek for data balancing.
2. **Visualization**: Visualized the dataset before and after applying SMOTETomek.
3. **Model Development**: Utilized both Random Forest and XGBoost models to predict machine failures.

## Results

Our findings indicate that XGBoost provided more precise predictions compared to Random Forest. These results underscore the importance of using advanced machine learning techniques and balanced datasets to improve the accuracy of predictive maintenance models.

## Files

- `dataset.csv`: The synthetic dataset file.
- `predictive_maintenance.ipynb`: Jupyter notebook containing the code for data analysis, model training, and evaluation.
- `README.md`: This file, providing an overview of the project.

## Conclusion

By applying SMOTETomek for data balancing and leveraging advanced machine learning models like XGBoost, we enhanced the accuracy of our predictive maintenance models. This project demonstrates the potential of using synthetic datasets to develop and evaluate predictive maintenance solutions in industrial settings.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
