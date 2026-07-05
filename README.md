Project Goals
Make Data Easy for Executives: Transform raw, messy Amazon sales data into simple, interactive numbers (like Total Sales, Orders, and Customers) so managers 
can make decisions instantly without digging through spreadsheets.

Spot Hidden Details: Use advanced tools (like custom tables with built-in neon data bars and growth tracking) to easily see small changes in sales that normal
charts usually hide.

Build a Clean, Modern Design: Move away from boring default templates. By using a dark-mode theme, organized grids, and shared filters across pages,
the dashboard looks like a smooth web app and prevents eye strain.


Screenshots

Overview
<img width="522" height="294" alt="image" src="https://github.com/user-attachments/assets/23646149-dd20-4271-8671-e56ce158a247" />

Sales Analysis
<img width="526" height="299" alt="image" src="https://github.com/user-attachments/assets/98d68fa0-5cd8-4413-be8b-c08b90b42929" />

Csuotmer Analysis
<img width="722" height="403" alt="image" src="https://github.com/user-attachments/assets/d4c928c3-6651-4b10-82ee-a9b4f63cf94a" />

Geographic Analysis
<img width="719" height="408" alt="image" src="https://github.com/user-attachments/assets/c96afd34-8bf1-4be8-ab2e-842ba5daf2a9" />

Trend Analysis
<img width="721" height="401" alt="image" src="https://github.com/user-attachments/assets/171d3206-333b-4153-a9de-275bbbd8c500" />


Some DAX Formuals

<img width="629" height="208" alt="image" src="https://github.com/user-attachments/assets/7de900e0-1f23-4ad5-817a-276914b71095" />

YoY Growth % = 
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)

Previous Year Sales = 
CALCULATE([Total Sales],SAMEPERIODLASTYEAR(DateTable[Date]))

Moving Average 3 Months = 
AVERAGEX(
    DATESINPERIOD(
        DateTable[Date],
        MAX(DateTable[Date]),
        -3,
        MONTH
    ),
    [Total Sales]
)
