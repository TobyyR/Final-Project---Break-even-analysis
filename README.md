# Final-Project---Break-even-analysis
## README for Forecasting and Analysis of Electricity and Fuel Data

### Project Overview
This project focuses on forecasting and analyzing electricity and fuel data using a variety of time series models. The project includes several key components:

1. **VAR (Vector AutoRegression) Model Fitting:** We use VAR models to predict future values based on historical electricity data, specifically from the United States. This model accounts for the interactions between multiple time series.
   
2. **Prophet Forecasting:** The Prophet model is utilized for forecasting time series data. This model is particularly effective for handling data with strong seasonal patterns and holidays.

3. **Break-even Analysis:** The project also includes a function to calculate the break-even point in kilometers and years when switching from a gasoline car to an electric car, based on various economic and usage factors.

4. **Data Collection:** The project retrieves monthly electricity price data for the United States using an API provided by the U.S. Energy Information Administration (EIA).

### Getting Started

#### Prerequisites
To run the project, you need to have the following installed:
- Python 3.7 or later
- Required Python libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `fbprophet`, `plotly`, and `requests`.

#### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/electricity-forecasting.git
   ```
2. Navigate to the project directory:
   ```bash
   cd electricity-forecasting
   ```
3. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

### Project Structure
- **main.py**: Main script to run the different analyses and forecasts.
- **forecasting.py**: Contains functions for VAR model fitting, Prophet forecasting, and plotting results.
- **break_even.py**: Includes the function to calculate the break-even point for switching from a gasoline car to an electric car.
- **data/**: Directory containing the raw and processed data files.
- **notebooks/**: Jupyter notebooks for exploratory data analysis (EDA) and model development.
- **README.md**: Project documentation.
- **requirements.txt**: List of required Python packages.
- **electro_us.csv**: The dataset containing monthly electricity prices in the U.S., collected via the EIA API.

### Data Preprocessing

The data preprocessing involves several steps to ensure that the datasets are in a suitable format for analysis and forecasting:

1. **Data Cleaning**: The time series data often contains duplicate records or missing values. These are removed or filled as necessary to ensure a continuous and clean dataset.
   
2. **Concatenation and Alignment**: The datasets from different sources (e.g., electricity prices and other economic indicators) are concatenated along a common time index to create a multi-variate time series that can be used in VAR models.

3. **Resampling**: The datasets are often resampled to a common frequency (e.g., monthly) to ensure consistency across different time series.

4. **Feature Engineering**: For the Prophet model, additional features such as holidays or events might be added to improve the model's accuracy.

### API Data Collection

The electricity price data is collected using the U.S. Energy Information Administration (EIA) API. A script (`api_data_collection.py`) is provided to automate the process of downloading and saving the data. The script queries the EIA API, retrieves data for the specified parameters, and saves it as a CSV file (`electro_us.csv`).

### Running the Analysis

1. **VAR Model Forecasting**:
   - Load your data and fit the VAR model by calling `fit_var_model_per_dataframe()`.
   - Forecast future values and visualize them using the `plot_forecasts()` function.

2. **Prophet Forecasting**:
   - Use the `prophet_forecast()` function to forecast time series data and visualize the results with Plotly.

3. **Break-even Analysis**:
   - Calculate the break-even point when switching to an electric car using `calculate_break_even()`.

### License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Acknowledgments
- U.S. Energy Information Administration (EIA) for providing the electricity price data.
- The developers of the `statsmodels` and `fbprophet` libraries for the forecasting tools used in this project.

### Contact
If you have any questions, feel free to open an issue or contact [your name](mailto:your.email@example.com).
