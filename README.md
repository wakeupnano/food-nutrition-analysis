# Food Product and Nutrition Analysis System

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3+-green.svg)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Latest-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> Big Data analytics project analyzing nutritional quality of 300,000+ food products from the Open Food Facts database

## 🎯Project Overview

This project implements a comprehensive nutrition analysis system that processes and analyzes over 300,000 food products from the Open Food Facts database. Using advanced data processing, feature engineering, and machine learning techniques, the system provides nutritional quality assessments, product classifications, and actionable insights for consumers and manufacturers.

### Key Achievements

- **Processed 300,000+ products** with 159 features from the Open Food Facts dataset
- **Implemented NRF9.3 scoring** - industry-standard nutritional quality metric
- **Built ML classifiers** achieving high accuracy in nutrition category prediction
- **Discovered patterns** linking ingredients to nutritional outcomes
- **Engineered features** including macronutrient ratios and caloric calculations

## Key Features

### 1. Nutritional Quality Assessment
- **NRF9.3 Implementation**: Modified Nutrient Rich Foods Index for standardized scoring
- **Automated Categorization**: Classification into Excellent, Good, Fair, and Poor categories
- **Product Comparison**: Enable informed choices within product categories

### 2. Data Processing Pipeline
- **Robust Cleaning**: Handling missing values across 159 features
- **Feature Engineering**: 
  - Caloric content calculation (proteins: 4 kcal/g, carbs: 4 kcal/g, fats: 9 kcal/g)
  - Macronutrient ratio computation
  - Nutrient density scoring
- **Quality Assessment**: Comprehensive data validation and filtering

### 3. Machine Learning Models
- **Logistic Regression Baseline**: Initial classification benchmark
- **Random Forest Classifier**: Advanced ensemble method for improved accuracy
- **Cross-Validation**: Rigorous model evaluation and hyperparameter tuning

### 4. Pattern Discovery
- **Ingredient Analysis**: Correlation between ingredients and nutrition
- **Category Trends**: Identifying formulation patterns across product types
- **Health Impact Grouping**: Clustering products by nutritional profile

## 🛠️ Technologies & Libraries

| Category | Technologies |
|----------|-------------|
| **Data Processing** | Pandas, NumPy, PandasSQL |
| **Machine Learning** | Scikit-learn, PyTorch |
| **Visualization** | Matplotlib, Seaborn, Plotly |
| **Data Source** | Kaggle API, Open Food Facts |
| **Development** | Jupyter Notebook, Python 3.8+ |

## 📊 Dataset Information

**Source:** [Open Food Facts - World Food Facts Dataset](https://www.kaggle.com/datasets/openfoodfacts/world-food-facts)

- **Size:** 300,000+ food products
- **Features:** 159 columns including nutritional values, ingredients, categories
- **Format:** TSV (Tab-Separated Values)
- **Encoding:** UTF-8

### Key Features Analyzed
- Macronutrients: proteins, carbohydrates, fats
- Micronutrients: vitamins, minerals
- Additives and ingredients
- Product categories and brands
- Nutrition grades and scores

## 🚀 Getting Started

### Prerequisites

```bash
# Python 3.8 or higher
python --version

# Jupyter Notebook
jupyter --version
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/food-nutrition-analysis.git
cd food-nutrition-analysis
```

2. **Create virtual environment**
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up Kaggle API** (for dataset download)
```bash
# Place your kaggle.json in ~/.kaggle/
mkdir ~/.kaggle
cp /path/to/kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
```

5. **Launch Jupyter Notebook**
```bash
jupyter notebook CIS_5450_Big_Data_Analytics_Project.ipynb
```

### Quick Start (Without Kaggle API)

If you prefer to download the dataset manually:
1. Visit [Open Food Facts Dataset](https://www.kaggle.com/datasets/openfoodfacts/world-food-facts)
2. Download `en.openfoodfacts.org.products.tsv`
3. Place in `data/` directory
4. Update the file path in the notebook

## 📁 Project Structure

```
food-nutrition-analysis/
│
├── Food_Nutritional_Analysis.ipynb             # Main analysis notebook
├── requirements.txt                            # Python dependencies
├── README.md                                   # This file
├── LICENSE                                     # MIT License
├── .gitignore                                  # Git ignore rules
│
├── data/                                       # Data directory
│   ├── README.md                               # Data documentation
│   └── .gitkeep                                # Keep directory in git
```

## 💡 Methodology

### Part 1: Data Loading and Exploration

1. **Dataset Acquisition**
   - Downloaded via Kaggle API using `kagglehub`
   - Loaded 300,000+ products with 159 features

2. **Data Quality Assessment**
   - Identified missing values across nutritional columns
   - Evaluated data completeness for key nutrients
   - Assessed data types and encoding issues

3. **Data Cleaning**
   - Filtered products with complete nutritional information
   - Handled missing values using domain-appropriate strategies
   - Removed duplicates and invalid entries

4. **Feature Engineering**
   - **Caloric Content**: Calculated from macronutrients
   - **Macronutrient Ratios**: Protein, carb, and fat percentages
   - **NRF9.3 Score**: Modified Nutrient Rich Foods Index
   - **Product Categories**: Automated nutritional categorization

### Part 2: Exploratory Data Analysis

- **Nutritional Distribution**: Analysis of nutrient profiles across categories
- **Correlation Analysis**: Relationships between nutrients and ingredients
- **Category Patterns**: Trends in product formulation
- **Quality Metrics**: Statistical assessment of nutrition scores

### Part 3: Machine Learning Models

- **Baseline Model**: Logistic Regression for classification
- **Advanced Model**: Random Forest with hyperparameter tuning
- **Validation**: Cross-validation and performance metrics
- **Feature Importance**: Identifying key nutritional predictors

## 📈 Key Findings

### Nutritional Insights

1. **Top Nutrient-Dense Foods**: Identified products with highest NRF9.3 scores
2. **Category Analysis**: Significant variation in nutrition quality across product types
3. **Ingredient Correlations**: Strong relationships between specific ingredients and nutritional outcomes
4. **Distribution Patterns**: Most products fall into "Fair" and "Good" categories

### Model Performance

- **Logistic Regression**: [Accuracy %] baseline performance
- **Random Forest**: [Accuracy %] improved classification
- **Key Features**: Macronutrient content and specific micronutrients most predictive

## 🎓 Academic Context

This project demonstrates practical application of big data analytics concepts:

- **Large-Scale Data Processing**: Handling 300,000+ records with 159 features
- **Feature Engineering**: Domain-specific transformations for nutrition science
- **ML Pipeline**: End-to-end workflow from data cleaning to model deployment
- **Statistical Analysis**: Rigorous evaluation of data quality and model performance

### Skills Demonstrated

- Data wrangling with messy, real-world datasets
- Feature engineering for domain-specific problems
- Machine learning classification techniques
- Statistical analysis and visualization
- Reproducible data science workflows

## 🔍 Sample Analysis

### NRF9.3 Scoring Implementation

```python
# Nutrient Rich Foods Index (NRF9.3)
# 9 nutrients to encourage, 3 nutrients to limit

nutrients_to_encourage = [
    'proteins_100g', 'fiber_100g', 'calcium_100g',
    'iron_100g', 'potassium_100g', 'vitamin_a_100g',
    'vitamin_c_100g', 'vitamin_d_100g', 'vitamin_e_100g'
]

nutrients_to_limit = [
    'saturated_fat_100g', 'sodium_100g', 'sugars_100g'
]

# Calculate weighted score
nrf_score = (sum_of_encouraged - sum_of_limited) / reference_values
```

### Nutritional Category Classification

```python
def categorize_nutrition(nrf_score):
    if nrf_score >= 75: return 'Excellent'
    elif nrf_score >= 50: return 'Good'
    elif nrf_score >= 25: return 'Fair'
    else: return 'Poor'
```

## Visualizations

The project includes comprehensive visualizations:

- Distribution of nutrition density scores
- Category-wise nutritional profiles
- Correlation heatmaps of nutrients
- Macronutrient composition charts
- Model performance metrics

## Future Enhancements

- [ ] Real-time nutrition scoring API
- [ ] Personalized recommendations based on dietary preferences
- [ ] Integration with barcode scanning
- [ ] Comparative analysis across countries/regions
- [ ] Time-series analysis of product formulation trends
- [ ] Deep learning models for ingredient analysis

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

This is an academic project, but suggestions and feedback are welcome!

- Open an issue for bugs or enhancement ideas
- Fork the repository and submit pull requests
- Share your insights or alternative approaches

## References

- [NRF9.3 Index Methodology](https://www.nutrientsreview.com/nrf)
- [Open Food Facts Database](https://world.openfoodfacts.org/)
- [Kaggle Dataset Documentation](https://www.kaggle.com/datasets/openfoodfacts/world-food-facts)