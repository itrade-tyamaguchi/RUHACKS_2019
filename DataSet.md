# **To get the dataset please see the Slack channel**

# Definitions
* BUYERID - Unique ID Number for the Buyer
* SELLERID - Unique ID Number for the Seller
* AUDIT_MTH - The month the transaction took place
* PRODUCTCODE - iTradeNetwork unique product ID for each supplier. There can be the same product across multiple suppliers with different product IDs.
* CATEGORYNAME - iTradeNetwork generated category that suppliers select. There can be the same product across multiple suppliers with different category names.
* DISPLAY_DESCRIPTION	- Supplier created description for their product. Often Unique
* Total_Qty	- Total quantity of product purchased in a given month
* AvgPrice	- Average price of product per unit purchased in a given month
* Order_Price - Total_Qty * AvgPrice

# Assumptions
* Remove unknown DISPLAY_DESCRIPTION
* Unassigned CATEGORYNAME is due to the fact, it's not a required box to check
* CATEGORYNAME "EDI", treat as unassigned

# Goals
## Determine:
* Anomaly Detection for mis-catagorized DISPLAY_DESCRIPTION greater than 2 sigma
* Anomaly Detection for Total_Qty variance by product greater than 2 sigma
* Anomaly Detection for AvgPrice variance by product greater than 2 sigma
* Shifts of same supplier to a different buyer. Selling to one buyer less than 10 unique months
* Shifts of same supplier to a different buyer. Moving volume from 1 buyer to another
* Trends in which suppliers could be most benefit by switching buyers
* Which buyers are paying the most. POV for suppliers. All in and seasonally
* Trends in which buyers could be most enriched by switching suppliers.
  * Which suppliers are selling cheap products
  * From the for buyers point of view
  * All in and seasonally
* Trends in which products could be most benefit by switching buyers
  * Which buyers are paying the most
  * From the suppliers point of view
  * All in and seasonally
* Trends in which products could be most enriched by switching suppliers
  * Which suppliers are selling cheap products
  * From the buyers point of view
  * All in and seasonally
* Predictive Analyses for Total_Qty by product by supplier
* Predictive Analyses for AvgPrice by product by supplier
* Predictive Analyses for when a buyer's volume will reach 0 and when a buyer's volume will increase (by intervals of 10%)
  * Assuming they adopt the "Trends" above and assuming they don't
