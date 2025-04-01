# ACME-Synthetic-Data-and-Sales-Optimization Alogrithm
The algorithm is free to use. Please give me credits 
# ACME Synthetic Data and Sales Optimization Algorithm

## Overview
This project generates a synthetic dataset and implements optimization algorithms for sales and margin maximization within the ACME company structure. The hierarchical levels include Portfolio, Geography, Category, Brand, and Segment, with constraints applied at different levels.

## Features
- **Synthetic Data Generation**: Creates structured data with realistic initial sales, margins, trends, and contributions.
- **Sales & Margin Optimization**:
  - Maximize Sales within constraints.
  - Maximize Margin within constraints.
  - Achieve a Sales Target while maximizing Margin.
  - Achieve a Margin Target while maximizing Sales.
- **5-Year Projections**: Generates and visualizes future sales and margin trends.
- **Constraint Handling**: Ensures min/max trends are valid and prevents invalid financial data.
- **Error Handling**: Prevents negative values and maintains logical consistency in constraints.

## Installation
Clone the repository and install required dependencies:
```bash
# Clone repository
git clone https://github.com/yourusername/acme-sales-optimizer.git
cd acme-sales-optimizer

# Install dependencies
pip install pandas numpy matplotlib
```

## Usage
### Generating Synthetic Data
```python
from data_generator import generate_synthetic_data

df = generate_synthetic_data()
print(df.head())
```

### Running Optimization Algorithms
#### 1. Maximize Sales
```python
from optimization import maximize_sales

optimized_sales = maximize_sales(df)
print(optimized_sales.head())
```

#### 2. Maximize Margin
```python
from optimization import maximize_margin

optimized_margin = maximize_margin(df)
print(optimized_margin.head())
```

#### 3. Hit a Sales Target While Maximizing Margin
```python
from optimization import optimize_sales_target

sales_target = 50000000  # Example target
optimized_sales_target = optimize_sales_target(df, sales_target)
print(optimized_sales_target.head())
```

#### 4. Hit a Margin Target While Maximizing Sales
```python
from optimization import optimize_margin_target

margin_target = 0.25  # Example target
optimized_margin_target = optimize_margin_target(df, margin_target)
print(optimized_margin_target.head())
```

### 5-Year Sales & Margin Projections
```python
from projections import five_year_projections, visualize_projections

annual_growth_limits = {1: 0.08, 2: 0.10, 3: 0.12, 4: 0.07, 5: 0.05}
projections_df, yearly_projections = five_year_projections(df, annual_growth_limits)
visualize_projections(yearly_projections)
```

## Visualization
The system generates a sales and margin trend over five years using Matplotlib.
```python
from projections import visualize_projections
visualize_projections(yearly_projections)
```

## Error Handling
- Ensures `min_trend <= max_trend` by swapping values if necessary.
- Prevents negative sales or margins.
- Handles unexpected input errors with clear messages.

## Contributing
Feel free to fork this repository and submit pull requests with improvements.

## License
This project is licensed under the MIT License.


