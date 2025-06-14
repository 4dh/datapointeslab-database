# Data Pointes Lab Database

<div align="center">
  <img src="assets/logo.png" alt="Data Pointes Lab" width="200"/>
  
  **Open-source database of pointe shoe specifications and characteristics for ballet dancers, fitters, and researchers.**
  
  [![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
  [![Data Version](https://img.shields.io/badge/Data%20Version-2024.06-blue.svg)]()
  [![Shoes Count](https://img.shields.io/badge/Shoes-375+-green.svg)]()
  [![Brands](https://img.shields.io/badge/Brands-15+-orange.svg)]()
</div>

## ⚠️ Important Disclaimers

**READ CAREFULLY BEFORE USING THIS DATA**

### Data Accuracy & Currency
- **Data may be outdated**: Pointe shoe specifications, availability, and pricing change frequently
- **No warranty**: We provide this data "as-is" without any guarantees of accuracy, completeness, or fitness for any purpose
- **Verify independently**: Always confirm specifications with manufacturers or authorized retailers before making purchasing decisions
- **Not professional advice**: This data is for informational purposes only and does not constitute professional fitting advice

### Liability Limitations
- **No responsibility for injuries**: We are not responsible for any injuries, damages, or adverse outcomes resulting from the use of this data
- **No responsibility for purchases**: We are not responsible for incorrect purchases, financial losses, or dissatisfaction with products
- **No responsibility for business decisions**: Commercial users assume full responsibility for any business decisions based on this data
- **Use at your own risk**: Users assume all risks associated with using this information

### Medical & Safety Considerations
- **Consult professionals**: Always consult qualified pointe shoe fitters and dance instructors
- **Individual needs vary**: Pointe shoe selection is highly individual and depends on many factors not captured in this data
- **Safety first**: Improper pointe shoe selection can lead to serious injury

## 📊 What's Included

This comprehensive dataset contains detailed specifications for **375+ pointe shoe models** from **15 major manufacturers**:

### Data Fields
- **Basic Information**: Brand, model, availability
- **Physical Characteristics**: Box shape, platform width, shank strength, vamp length
- **Fit Details**: Wing height, heel height, arch support
- **Performance**: Durability ratings, intended foot shapes
- **Commercial**: Price ranges, available sizes/widths, customization options
- **Materials**: Composition details where available

### Supported Brands
- Bloch
- Capezio  
- Chacott
- FR Duval
- Freed of London
- Gaynor Minden
- Grishko/Nikolay
- Merlet
- Mirella
- R-Class
- Russian Pointe
- Sansha
- So Danca
- Suffolk
- Wear Moi

## 📁 Repository Structure

```
datapointeslab-database/
├── README.md                    # This file
├── LICENSE                      # CC BY 4.0 License
├── CHANGELOG.md                 # Version history
├── data/
│   ├── pointe_shoes.json       # Main dataset (JSON format)
│   ├── STANDARD_POINTES_DB_CONSOLIDATED.xlsx  # Excel format
│   └── schema.json             # Data schema documentation
├── docs/
│   ├── DATA_DICTIONARY.md      # Field definitions
│   ├── METHODOLOGY.md          # Data collection methods
│   └── CONTRIBUTING.md         # How to contribute
├── scripts/
│   ├── validate_data.py        # Data validation scripts
│   └── export_formats.py       # Format conversion utilities
└── assets/
    ├── logo.png                # Data Pointes Lab logo
    └── logo_inverted_small_logo.png  # Inverted logo variant
```

## 🚀 Quick Start

### Download the Data

**JSON Format** (Recommended for developers):
```bash
curl -O https://raw.githubusercontent.com/yourusername/datapointeslab-database/main/data/pointe_shoes.json
```

**Excel Format** (Recommended for researchers):
```bash
curl -O https://raw.githubusercontent.com/yourusername/datapointeslab-database/main/data/STANDARD_POINTES_DB_CONSOLIDATED.xlsx
```

### Using the Data

#### Python Example
```python
import json
import pandas as pd

# Load JSON data
with open('pointe_shoes.json', 'r') as f:
    shoes_data = json.load(f)

# Convert to DataFrame
df = pd.DataFrame(shoes_data)

# Example: Find all shoes with medium box shape
medium_box_shoes = df[df['box_shape'] == 'Medium']
print(f"Found {len(medium_box_shoes)} shoes with medium box shape")
```

#### R Example
```r
library(jsonlite)
library(dplyr)

# Load data
shoes_data <- fromJSON("pointe_shoes.json")

# Example: Analyze price ranges by brand
price_analysis <- shoes_data %>%
  group_by(brand) %>%
  summarise(
    avg_min_price = mean(price_min, na.rm = TRUE),
    avg_max_price = mean(price_max, na.rm = TRUE)
  )
```

## 📚 Data Sources

This database aggregates information from multiple sources to provide comprehensive pointe shoe specifications:

| Source Type | Description | Coverage | Last Updated | Reliability |
|-------------|-------------|----------|--------------|-------------|
| **Manufacturer Websites** | Official product specifications and catalogs | All brands | 2024-06 | High |
| **Authorized Retailers** | Product listings and detailed specifications | Major models | 2024-06 | High |
| **Dance Supply Stores** | Professional fitting guides and product details | Popular models | 2024-05 | Medium-High |
| **Professional Fitters** | Expert knowledge and fitting experience | Select models | 2024-04 | High |
| **Ballet Schools** | Institutional purchasing guides and recommendations | Student models | 2024-03 | Medium |
| **Dancer Communities** | User reviews and real-world experience | Various models | 2024-06 | Medium |
| **Industry Publications** | Trade magazines and professional reviews | New releases | 2024-05 | Medium-High |
| **Historical Archives** | Discontinued models and legacy specifications | Vintage models | 2024-02 | Medium |

### Source Verification Process

1. **Primary Sources**: Manufacturer websites and official documentation (highest priority)
2. **Cross-Reference**: Multiple sources verified against each other
3. **Expert Review**: Professional fitters consulted for accuracy
4. **Community Validation**: Experienced dancers provide real-world feedback
5. **Continuous Updates**: Regular monitoring of source changes

### Data Quality Notes

- **Manufacturer Data**: Most reliable for current models, may lack detailed fitting characteristics
- **Retailer Data**: Good for availability and pricing, specifications may vary
- **Professional Input**: Excellent for fitting nuances, limited to fitter experience
- **Community Data**: Valuable for real-world performance, subject to individual variation
- **Historical Data**: Important for completeness, may be less accurate due to age

### Known Limitations

- Some discontinued models may have incomplete specifications
- Pricing data reflects approximate ranges and varies by region
- Customization options may not reflect all available variations
- New model releases may have limited initial data

## 📈 Applications

This dataset has been used for:

- **Research**: Academic studies on ballet footwear and injury prevention
- **E-commerce**: Product recommendation systems
- **Education**: Teaching data science with real-world ballet data
- **Mobile Apps**: Pointe shoe selection and comparison tools
- **Analytics**: Market analysis and trend identification

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines.

### Ways to Contribute
- **Data Updates**: Submit corrections or new shoe information
- **Documentation**: Improve explanations and examples
- **Validation**: Help verify data accuracy
- **Translations**: Translate documentation to other languages

## 📄 License & Attribution

This work is licensed under [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

### Required Attribution
When using this data, please include:

```
Data from Data Pointes Lab Database
https://github.com/yourusername/datapointeslab-database
Licensed under CC BY 4.0
```

### Commercial Use
Commercial use is permitted under CC BY 4.0, but you must:
- Provide proper attribution
- Indicate if changes were made
- Not imply endorsement by Data Pointes Lab

## 🔗 Related Projects

- **[Data Pointes Lab](https://datapointeslab.com)** - Interactive pointe shoe fitting tool
- **[Pointe Shoe Fitter API](https://github.com/yourusername/pointe-shoe-api)** - RESTful API for this data

## 📞 Contact & Support

- **Website**: [datapointeslab.com](https://datapointeslab.com)
- **Issues**: [GitHub Issues](https://github.com/yourusername/datapointeslab-database/issues)
- **Email**: support@datapointeslab.com

## 🏷️ Version History

- **v2024.06**: Initial public release (375 shoes, 15 brands)
- **v2024.05**: Beta testing phase
- **v2024.04**: Data collection and validation

## ⚖️ Legal Notice

This database is provided for informational and educational purposes only. The creators and maintainers of this database:

1. **Make no warranties** about the accuracy, completeness, or reliability of the data
2. **Disclaim all liability** for any damages arising from the use of this data
3. **Do not endorse** any particular brands, products, or retailers
4. **Are not responsible** for any commercial transactions or decisions based on this data
5. **Recommend professional consultation** for all pointe shoe fitting decisions

By using this data, you acknowledge that you have read, understood, and agree to these terms and disclaimers.

---

<div align="center">
  <img src="assets/logo_inverted_small_logo.png" alt="Data Pointes Lab" width="100"/>
  
  **Data Pointes Lab** - Empowering dancers through data
</div> 