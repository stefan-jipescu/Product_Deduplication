# Product Deduplication

## Overview  
This project processes a dataset containing multiple rows for a common key. The data was extracted using Large Language Models (LLMs), which resulted in data duplication—causing a single product to have multiple entries.  

## Technologies Used  
- **Python** – Core programming language  
- **Pandas** – Data manipulation and processing  
- **NumPy** – Numerical operations and data structuring (`np.ndarray` for handling array-based data)  

## Methodology  
Through data analysis, we discovered that most columns contained NumPy arrays. To handle this, we used `np.ndarray` along with `groupby` to aggregate data efficiently.  

- **String and Numeric Columns:** We generated unique lists for each entry, eliminating duplicates while preserving all relevant information per product.  
- **Dictionary Columns:** We created a list with unique elements for each key. If a key was missing, we added it to ensure data completeness.  
- **Price Column Exception:** Instead of deduplicating price values, we allowed them to be aggregated and averaged, ensuring a more accurate representation of the product's price.  
- **Final Output:** For all other columns, we preserved unique characteristics to create a detailed and enriched product description.  

## Goal  
The final output is an updated dataset where duplicates are consolidated into a single, enriched entry per product—maximizing available information while ensuring uniqueness and data integrity.
