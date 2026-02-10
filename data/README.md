# Data Directory

## Dataset Information

This project uses the **Open Food Facts - World Food Facts** dataset from Kaggle.

### Dataset Details

- **Source:** [Kaggle - Open Food Facts Dataset](https://www.kaggle.com/datasets/openfoodfacts/world-food-facts)
- **Size:** 300,000+ food products
- **Features:** 159 columns
- **Format:** TSV (Tab-Separated Values)
- **File:** `en.openfoodfacts.org.products.tsv`
- **Encoding:** UTF-8

### Key Features

#### Nutritional Information (per 100g)
- Macronutrients: proteins, carbohydrates, fats
- Micronutrients: vitamins, minerals
- Energy values: calories, kilojoules
- Specific nutrients: fiber, sodium, sugars, saturated fats

#### Product Information
- Product name and brand
- Categories and tags
- Ingredients list
- Countries of sale
- Nutrition grades
- Additives and allergens

### Data Schema

The dataset contains 159 columns including:

**Identifiers:**
- `code`: Product barcode
- `product_name`: Name of the product
- `brands`: Brand information

**Nutritional Values (all per 100g):**
- `energy_100g`: Energy content
- `proteins_100g`: Protein content
- `carbohydrates_100g`: Carbohydrate content
- `fat_100g`: Fat content
- `fiber_100g`: Fiber content
- `sodium_100g`: Sodium content
- `sugars_100g`: Sugar content
- `saturated-fat_100g`: Saturated fat content
- And many more micronutrients...

**Categories:**
- `categories`: Product category tags
- `main_category`: Primary category

**Other:**
- `ingredients_text`: Full ingredients list
- `nutrition_grade_fr`: Nutrition score (A-E)

## Setup Instructions

### Option 1: Kaggle API (Recommended)

1. **Install Kaggle CLI:**
```bash
pip install kaggle kagglehub
```

2. **Set up Kaggle credentials:**
   - Go to https://www.kaggle.com/settings
   - Scroll to "API" section
   - Click "Create New API Token"
   - Save `kaggle.json` to `~/.kaggle/`

3. **Download dataset (automated in notebook):**
```python
import kagglehub
path = kagglehub.dataset_download("openfoodfacts/world-food-facts")
```

### Option 2: Manual Download

1. Visit [Open Food Facts Dataset](https://www.kaggle.com/datasets/openfoodfacts/world-food-facts)
2. Click "Download" (requires Kaggle account)
3. Extract `en.openfoodfacts.org.products.tsv`
4. Place in this `data/` directory
5. Update the notebook file path if needed

## Data File Organization

```
data/
├── README.md                              # This file
├── .gitkeep                               # Keep directory in Git
├── en.openfoodfacts.org.products.tsv     # Main dataset (not tracked in Git)
└── processed/                             # Processed/cleaned data
    ├── clean_nutrition_data.csv          # Cleaned dataset
    └── features_engineered.csv           # With engineered features
```

## Data Not Included in Repository

**Important:** Due to the large size (>500 MB), the raw data file is **not included** in this GitHub repository.

The `.gitignore` file is configured to exclude:
- `*.tsv`
- `*.csv` (in data directory)
- `*.json` (in data directory)
- All files in `data/` except README and .gitkeep

You must download the dataset yourself using one of the methods above.

## Data Quality Notes

### Known Issues
- Many missing values in micronutrient columns
- Inconsistent category naming
- Some products have incomplete nutritional information
- Text fields may contain multiple languages

### Data Cleaning Applied
- Filtered for products with complete macronutrient data
- Removed duplicates based on product code
- Standardized nutrition values to per 100g basis
- Handled missing values using domain-appropriate strategies

## Citation

If you use this dataset, please cite:

```
Open Food Facts. (2023). World Food Facts.
Kaggle. https://www.kaggle.com/datasets/openfoodfacts/world-food-facts
```

## License

The Open Food Facts database is made available under the Open Database License (ODbL).
Individual contents are available under the Database Contents License (DbCL).

More info: https://world.openfoodfacts.org/data

## Support

For dataset-specific questions:
- Open Food Facts: https://world.openfoodfacts.org/
- Kaggle Dataset Page: https://www.kaggle.com/datasets/openfoodfacts/world-food-facts

For project-specific questions, see main README.md
