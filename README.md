
**##Overview**
A four-page Power BI report on Zenith Bank's FY2020 and FY2021 results, comparing the Bank with the Group (Bank plus subsidiaries). It looks at income, costs, impairment and profit, and explains why Group profit grew only 6.1% while operating income grew 14.2%.

**##Key findings (Group, ₦ billions)**
Operating income grew 14.2% (551.4 to 629.8) and operating costs 13.1% (256.0 to 289.5), so cost-to-income edged down from 46.4% to 46.0%.
Growth came from fees (+31%) and trading gains (+38%), not lending: net interest income grew only 7%.
Impairment charges rose about 52%, from 13.2% to 18.7% of net interest income.
Bank profit after tax grew 17.8% against 6.1% for the Group, because the subsidiaries' contribution fell from 32.7 to 11.4.
Report pages
Entity and Trend Analysis: Bank vs Group profit, impairment and subsidiary contribution
Executive Summary: gross earnings, interest income, net interest income and profit
Revenue and Cost Deep Dive: operating income and costs by line, and the cost-to-income ratio
Income Statement Detail: line-by-line difference between Group and Bank
Data

Source: Zenith Bank audited financial statements (FY2021 report, including FY2020 comparatives) from the Nigerian Exchange (NGX). Figures are in ₦ millions and shown in ₦ billions.

**##Tools**
Excel: extracted the raw figures from the annual report and organised them into a table.
SQL Server (SSMS): stores the data in a star schema (Dim_Line_Item and Fact_Financials). When Power BI showed totals three times too high (Group 2021 profit after tax of 733,674 against 244,558 reported), I queried the table, found every record loaded three times, and removed the extra copies with a ROW_NUMBER() CTE, keeping one row per line item, entity and year. Totals then matched the audited statements.
Power Query: transformed the data and loaded it into Power BI.
Power BI: data model, four report pages, slicers and interactions.
DAX: measures for PAT growth (Bank and Group), impairment loss and impairment as a percentage of net interest income, cost-to-income ratio, operating income and costs by named line items, Group minus Bank contribution, and the ₦ millions to ₦ billions conversion.
Limitations
Two years of data, so this is a comparison and not a trend.
The reasons for the subsidiary decline still need checking against the report notes.
