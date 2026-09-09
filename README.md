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

## Rules and Standards
## Phases in Data Modelling
## Steps
* Building dimensions
* Building facts
* Measures
* RLS
## Conclusion
