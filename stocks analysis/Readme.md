# 📊 HATVP Stock Analysis Notebooks

## Overview

This project involves analyzing the stock participation data from French politicians' declarations, sourced from the High Authority for the Transparency of Public Life (HATVP). The analysis is divided into two main parts, each documented in a separate Jupyter Notebook. 🚀

**Note:** This is a work in progress (WIP), and more analysis notebooks will follow. 📚

## Part 1: Extraction and Cleaning 🧹

### Notebook: `HATVP - Stock analysis.ipynb`

#### Objectives
1. **Extract Data**: Load the dataset from the Hugging Face Hub and convert it to a pandas DataFrame.
2. **Parse Declarations**: Extract stock participation data from JSON strings contained within the dataset.
3. **DataFrame Creation**: Create a DataFrame for each declaration, capturing relevant stock information.
4. **Concatenate DataFrames**: Combine individual DataFrames into a single comprehensive DataFrame.
5. **Data Cleaning**: 
   - Standardize names and surnames by converting them to uppercase.
   - Convert date columns to datetime format.
   - Create a unique identifier for each declarant based on their name, surname, and birthdate.
   - Convert numeric columns to appropriate data types.

#### Key Functions
- `get_stock_df(string_declaration)`: Parses a single JSON string of a declaration to extract stock data and returns it as a DataFrame.

#### Steps
1. **Load Dataset**: Load the dataset into a pandas DataFrame.
2. **Parse Declarations**: Iterate through the dataset, parsing each declaration to extract stock information.
3. **Concatenate DataFrames**: Combine the list of DataFrames into a single DataFrame.
4. **Data Cleaning**: Standardize text fields, convert date fields, create unique identifiers, and convert numeric fields.

#### Output
The cleaned and formatted dataset is then pushed back to the Hugging Face Hub for further analysis.

## Part 2: Analysis and Inference 🔍

### Notebook: `HATVP - Stock analysis - Part 2.ipynb`

#### Objectives
1. **Filter Data**: Ensure each declarant has only their latest declaration included.
2. **Count Company Names**: Clean and format company names, then count occurrences.
3. **Fix Fuzzy Names**: Use basic text processing and GPT-3.5-turbo to correct company names.
4. **Analyze Popular Stocks**: Identify the most commonly declared stocks among politicians.

#### Steps
1. **Filter Latest Declarations**: 
   - Identify the latest declaration for each declarant.
   - Filter the dataset to keep only these latest declarations.
2. **Clean Company Names**: 
   - Remove accents, replace certain characters, and simplify names to the first two words.
3. **Count Occurrences**: Count the frequency of each cleaned company name.
4. **Correct Company Names**: Use OpenAI's GPT-3.5-turbo to infer the correct names of companies with fuzzy or incorrect entries.
5. **Analyze Data**: Generate a bar plot to visualize the top 30 most popular stocks among the declarations.

#### Visualization
- A bar plot of the top 30 most popular stocks is created using seaborn.

#### Output
- The cleaned dataset with inferred company names is pushed back to the Hugging Face Hub for further use.

## Conclusion

These notebooks perform a comprehensive analysis of stock participation data from French politicians' declarations. The first notebook focuses on extracting, cleaning, and preparing the data, while the second notebook delves into analyzing and correcting company names, providing insights into the most popular stocks among the politicians. The final datasets are uploaded to the Hugging Face Hub for accessibility and further analysis. Stay tuned for more analysis notebooks! 📈  

Our current recommendation to the HATVP is to ask for a valid "ISIN" when a declarant is filling-in publicly traded stocks.  
