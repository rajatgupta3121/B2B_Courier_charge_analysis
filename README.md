# B2B Courier Charges Accuracy Analysis

## Overview
This project aims to analyze and validate the accuracy of courier charges in a B2B setting by comparing multiple datasets, including order reports, SKU master data, pincode mappings, and courier invoices. By performing this analysis, we ensure that invoicing is correct and discrepancies in courier charges are identified for corrective action.

## Objectives
- **Ensure Invoice Accuracy:** Validate whether invoiced courier charges align with predefined courier company rates.
- **Identify Discrepancies:** Detect inconsistencies in pricing, weight calculations, and delivery charges.
- **Optimize Costs:** Provide insights to optimize courier service costs and minimize overcharges.
- **Improve Operational Efficiency:** Streamline the courier billing process and improve financial transparency.

## Datasets Used
1. **Order Report** (`Order Report.csv`): Contains details about customer orders, including SKU IDs, weight, and billed charges.
2. **SKU Master** (`SKU Master.csv`): Provides metadata about SKUs, including their names, weight categories, and applicable charges.
3. **Pincode Mapping** (`pincodes.csv`): Maps pincodes to respective regions and categorizes delivery zones.
4. **Courier Invoice** (`Invoice.csv`): Contains data on billed courier charges per order and shipment details.
5. **Courier Company Rates** (`Courier Company - Rates.csv`): Lists standard courier charges across different weight categories and service providers.

## Steps in Analysis
### 1. Data Preprocessing & Cleaning
- Dropped unnamed columns with null values.
- Standardized column names for consistency.
- Merged order reports and SKU master datasets using the SKU column.

### 2. Data Merging & Integration
- Removed duplicate entries from the pincode mapping dataset based on `Customer Pincode`.
- Extracted unique customer pincodes and created a new dataset (`abc_courier`).
- Selected key columns (`Order ID`, `Customer Pincode`, `Type of Shipment`) from the courier invoice dataset.
- Merged the `courier_abc` dataset with `abc_courier` using `Customer Pincode` as the primary key.

### 3. Courier Charge Validation
- Compared invoiced charges with the standard courier company rates.
- Checked for discrepancies between charged and expected rates.
- Analyzed weight-based pricing variations.
- Identified overcharges and undercharges across different orders.

### 4. Reporting & Insights
- Generated a summary report highlighting incorrect charges and anomalies.
- Recommended corrective actions for future invoice accuracy.
- Provided cost optimization suggestions to reduce excess courier charges.

## Technologies Used
- **Python** for data analysis and automation.
- **Pandas** for dataset manipulation and merging.
- **Jupyter Notebook** for executing and visualizing the analysis.
- **Matplotlib & Seaborn** for data visualization.
- **NumPy** for numerical computations.

## How to Run
1. Install necessary dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
2. Open the Jupyter Notebook:
   ```bash
   jupyter notebook B2B_Courier_charge_analysis_py.ipynb
   ```
3. Run all cells to perform the analysis.

## Expected Outcomes
- **Identification of incorrect courier charges** in invoices.
- **Ensured compliance with courier rate structures** by validating against the standard rate chart.
- **Optimized courier cost recommendations** to improve profitability.
- **Enhanced decision-making** for financial and logistics teams to streamline the billing process.

## Future Enhancements
- Automate the courier charge validation process using machine learning.
- Develop a real-time dashboard to visualize discrepancies and cost trends.
- Integrate with ERP systems for automated validation.

## Contributors
- **Rajat Gupta**
- Open for collaboration! Contributions, suggestions, and feedback are welcome.

## License
This project is open-source and available under the MIT License.

