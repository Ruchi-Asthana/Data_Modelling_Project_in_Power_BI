# Data Modelling Project | Power BI
## Project Overview
In this project, we work in Power BI with an unoptimized nightmare of a data model which has 23 messy tables, too many relationships and bad filters. 
We work to build a clean, healthy star schema data model that we can trust to deliver performance optimization in our reports and dashboards.
In the course of the project, we begin by exploring and understanding the dataset provided, transform the tables given into _dimensions_ and _facts_ 
and build our model along with the Date table and some core measures. Finally, we wrap up by applying the Row Level Security (RLS) mechanism 
on top of our model and perform a final validation.
## Dataset Description
The dataset is an Excel file that consists of 23 tables (worksheets):
1. **Address**: AddressID, Street, CityName
2. **CAMPAIGN_LOG**: CampaignName, Channel, StartDate, EndDate, Budget, Date, Impressions, Clicks, Spend
3. **CUST_MASTER**: CustomerID, CustomerName, Segment, AddressID, AccountManager, PaymentTerms, hash_key, source_id
4. **INVOICES**: InvoiceID, OrderID, CustomerName, InvoiceDate, Amount
5. **ORDERS_2025**: OrderID, LegacyRef, CustomerName, CustomerCity, RegionName, ShipToCity, BillToCity, OrderDate, OrderChannel, Status, Priority, OrderTotal, 	OrderNotes, GiftMessage, SourceFile
6. **ORDERS_2026**: OrderID, CustomerName, CustomerCity, RegionName, ShipToCity, BillToCity, OrderDate, OrderChannel, Status, Priority, OrderTotal, OrderNotes, 	GiftMessage
7. **Sheet1**: ShipmentID, OrderID, ShipMode, ShipDate, DeliveryDate
8. **campaign_skus**: CampaignName, PromotedSKUs
9. **cities**: CityName, RegionName
10. **customer_contacts**: CustomerID, ContactName, Email, IsPrimary
11. **dim_order**: OrderID
12. **exchange_rates**: Currency, Rate, Date
13. **inventory**: ProductName, 2025-01, 2025-02, 2025-03, 2025-04, 2025-05, 2025-06, 2025-07, 2025-08, 2025-09, 2025-10, 2025-11, 2025-12
14. **invoice_lines**: InvoiceLineID, InvoiceID, ProductName, Amount
15. **order_line_items**: LineID, OrderID, ProductName, Quantity, UnitPrice, UnitCost, DiscountPct, LineTotal
16. **payments**: PaymentID, InvoiceID, CustomerName, PayDate, Amount
17. **products**: ProductCode, ProductName, Brand, SubcategoryName, UnitPrice, PrimarySupplier, ProductDescription, hash_key, source_id
18. **regions**: RegionName
19. **sales_targets**: Period, TargetRevenue
20. **security**: UserEmail, Region
21. **shipments**: ShipmentID, OrderID, ShipMode, ShipDate, DeliveryDate
22. **subcategories**: CategorySubcategory
23. **user_details**: UserID, CreditLimit, Phone
## Nightmare Datamodel

<img width="1527" height="960" alt="nightmare_datamodel" src="https://github.com/user-attachments/assets/03c8e607-4f72-42bd-8edb-b80e7a6c1da8" />

## Rules and Standards applied
Rules:
1. Explore before building
  * Analyze the business
  * Explore the processes
  * Understand the data 
2. Know the **grain**
  * Make clear what one row represents.
  * A dimension row = one customer
  * A fact row = one sale
3. Set standards up front and follow till the end.
  * Naming standards for tables and columns, prefixes, suffixes.
4. Every column _earns its place_. If it doesn't help the report, drop it. This results in lighter files and fewer fields so less confusing to wade through.
5. Protect the numbers like _totals_, re-check after every change.
6. Build a **Star Schema**: a _fact_ in the middle and _dimensions_ around it.

Standards:
* Standard Language:
  * One language everywhere - English
* Standard Naming: **snake_case**
  * all lowercase joined with _ (underscore)
  * for example, CustomerName = customer_name
* Standard Tables: **fact_** for fact tables and **dim_** for dimension tables
  * for example, sales = fact_sales | customer = dim_customer
* Standard Keys:
  * _key: we make it | _id: from the source
  * for example, id_customer = customer_id | CustKey = customer_key
* Standard Friendly Names: readable names, not cryptic codes
  * for example, cust_nm = customer_name | tot_rev = total_revenue
## Phases in Data Modelling
* Phase 1: Prepare and Explore
  * Explore the messy model.
  * Prepare the workspace.
  * Understand the business.
  * Understand the data.
  * Spot dimensions vs facts.
* Phase 2: Dimensions
  * Build clean dimensions, one by one.
  * Group the tables for one entity.
  * Reshape into one clean dimension.
  * Clean it to the standards.
  * Repeat for every dimension.
* Phase 3: Facts
  * Pick an event, read its grain.
  * Build the fact from the details.
  * Connect every dimension.
  * Test so the numbers never break.
* Phase 4: Polish
  * Re-check the standards.
  * Add the date dimension.
  * Build the measures.
  * Add row-level security
  * Final validation
## Final Model

<img width="1432" height="738" alt="final_model" src="https://github.com/user-attachments/assets/ac15b757-7785-42bf-9d8e-aea61efe410e" />

