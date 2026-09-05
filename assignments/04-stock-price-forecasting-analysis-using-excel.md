---
layout: default
title: "Stock Price Forecasting Analysis Using Excel"
permalink: /assignments/04-stock-price-forecasting-analysis-using-excel/
---

# Assignment 2 – Forecasting with Excel

- **Due:** Saturday 12:00 AM
- **Total Points:** 100


> 🎥 **Recording your video:** Use Microsoft Clipchamp to record your camera, microphone, and screen, then export the completed recording as an `.mp4` file. Follow the [Microsoft Clipchamp Recording Guide](https://is251-course-guides.dobinyim.chatgpt.site/clipchamp-recording) before submitting in Moodle.

## 📈 Overview

In this assignment, you will investigate factors that may be associated with a publicly traded company’s stock price.

You will collect approximately two years of daily stock prices from Yahoo Finance, combine the stock data with three predictor variables, and use Excel to run a regression analysis. You will then explain what the results mean.

The purpose is not to predict whether someone should buy or sell the stock. Instead, you will practice preparing real-world data and determining whether selected variables are meaningfully related to stock-price changes.

## 🎯 Learning Objectives

By completing this assignment, you will learn how to:

- Collect and organize historical data from an online source.
- Clean copied data using Excel tables, sorting, filters, and formatting.
- Combine datasets by matching their Date columns.
- Use `VLOOKUP` with an exact match.
- Create and format a line chart.
- Run a multiple regression using the Analysis ToolPak or Microsoft Copilot.
- Interpret R-squared and p-values.
- Evaluate the limitations of a statistical model.
- Communicate your process and findings in a short video.

## 1. Choose a Company

Select one publicly traded company from one of these indices:

- Dow Jones Industrial Average
- NASDAQ-100
- S&P 500

Include a brief company background:

- Company name and stock symbol
- Industry
- Primary products or services
- Reason you selected the company

## 2. Collect Stock Data from Yahoo Finance

1. Visit [Yahoo Finance](https://finance.yahoo.com/) and search for your company.
2. Open **Historical Data**.
3. Select **daily data** covering the most recent two years, ending in the current month.
4. Copy and paste the historical data into a new Excel worksheet.

Direct downloading may require a paid Yahoo Finance plan, so you may copy the displayed historical data and paste it into Excel.

Your dataset must contain:

- Approximately two years of daily trading data
- At least **500 stock-price records**
- Only the **Date** and **Close** columns

Delete Open, High, Low, Adjusted Close, Volume, and all other unnecessary columns.

Rename the Close column so that it clearly identifies the company—for example, `AAPL Close`.

## 3. Clean and Organize the Stock Data

Use the following Excel features:

- **Excel Table (`Ctrl+T`)** to organize the dataset
- **Sort** to arrange dates from oldest to newest
- **Remove Duplicates** to ensure each date appears once
- **Date Formatting** to ensure Excel recognizes the dates correctly
- **Filters** to find blanks, errors, or unusual values
- **Descriptive worksheet names** such as `Stock Data`

Before continuing, confirm that:

- The Date column contains valid Excel dates.
- The Close column contains numbers.
- No headings or notes appear between data rows.
- The worksheet contains at least 500 stock-price records.

## 4. Choose Three Predictor Variables

Select at least three variables that might be associated with the company’s closing stock price.

Possible predictors include:

- A market index such as the S&P 500 or NASDAQ
- A competitor’s stock price
- Interest rates
- Oil, gold, or another relevant commodity price
- A currency exchange rate
- Another measurable economic or industry variable

Each predictor must contain:

- A Date column
- A numeric value column
- Data covering approximately the same two-year period

Place each predictor dataset on a separate worksheet and provide its source.

## 5. Merge the Predictor Data Using VLOOKUP

Return to the stock-data worksheet and add one column for each predictor.

Your final table should have this structure:

| Date | Stock Close | Predictor 1 | Predictor 2 | Predictor 3 |
|---|---:|---:|---:|---:|

Use `VLOOKUP` to match each predictor with the stock data by Date.

Example using an Excel table:

```excel
=VLOOKUP([@Date],'Market Index'!$A$2:$B$600,2,FALSE)
```

Example using regular cell references:

```excel
=VLOOKUP(A2,'Market Index'!$A$2:$B$600,2,FALSE)
```

In the formula:

- `A2` or `[@Date]` is the stock date.
- The first column in the lookup range must contain predictor dates.
- The second column must contain predictor values.
- `2` returns the predictor value.
- `FALSE` requires an exact date match.

Copy the formula down for every stock record. Repeat the process for all three predictors.

### Check Your Matches

Use Excel’s filters and error checking to find `#N/A` results. These usually indicate that a predictor did not have data for that date.

Do not replace missing values with zero. A zero would be treated as a real measurement and could distort the regression. Check the date formats first, and then remove rows that still contain missing predictor values.

## 6. Create a Stock-Price Chart

Create a line chart showing how the company’s closing stock price changed during the two-year period.

The chart must include:

- A descriptive title
- Date on the horizontal axis
- Closing price on the vertical axis
- Clearly labeled axes
- A readable and professional format

## 7. Run the Regression

Choose one of the following methods.

### Option A: Analysis ToolPak

Use Excel’s **Data Analysis ToolPak** to run a regression:

- **Dependent variable:** the company’s closing stock price
- **Independent variables:** the three predictor columns

Place the regression output on a new worksheet named `Regression Results`.

### Option B: Microsoft Copilot

Open the completed table in Excel 365 and select Copilot. Replace the bracketed items in this prompt with your exact column names:

> Using my Excel table, run a multiple regression with **[Company Close]** as the dependent variable and **[Predictor 1]**, **[Predictor 2]**, and **[Predictor 3]** as the independent variables. Exclude rows with missing values. Show the number of observations, coefficients, R-squared, adjusted R-squared, and p-values. Explain the results in simple language and identify any data-quality concerns.

Review Copilot’s response and confirm that it used the correct dependent and independent variables. Place or copy the results into a worksheet named `Regression Results`.

## 8. Interpret the Results

Provide concise written answers to the following questions:

1. What company and stock symbol did you select?
2. Which three predictors did you select, and why might each be related to the stock price?
3. What is the model’s R-squared value?
4. In your own words, what does the R-squared value indicate?
5. Which predictors have p-values below `0.05`?
6. Based on the p-values, which predictors appear statistically significant?
7. Did any results surprise you? Explain briefly.
8. What is one important limitation of your data or regression model?
9. Did you use the Analysis ToolPak or Microsoft Copilot?

Do not provide a Buy, Sell, or Hold recommendation.

## 📤 Submission Requirements

Submit the following:

- Your completed Excel workbook (`.xlsx`)
- [Complete the Excel Forecasting response form](https://forms.cloud.microsoft/Pages/ResponsePage.aspx?id=jwquMN88_USvNCeL9jm4XZxxOpXwxOZDse9j-9iVSRdUNzE4NEdNTTBUQjFPSUZBNFFEMEhSQ0RWUy4u)
- A **3–5 minute video demonstration**

The Excel workbook must contain:

- The original stock-data worksheet
- Separate worksheets for predictor data
- The final merged dataset
- Working `VLOOKUP` formulas
- A stock-price line chart
- Regression results
- Clearly labeled worksheets and columns
- Citations or links for all data sources

## 🎥 Video Demonstration

In your video:

1. Introduce your selected company and predictors.
2. Show the stock data copied from Yahoo Finance.
3. Confirm that you retained only Date and Close.
4. Show at least one working `VLOOKUP` formula.
5. Explain how the formula matches records by Date.
6. Show your chart and regression results.
7. State whether you used the Analysis ToolPak or Copilot.
8. Explain R-squared and at least one p-value in your own words.
9. Identify one limitation of your analysis.

Your video should demonstrate your own workbook and your understanding of the process—not simply read the assignment instructions.

## ✅ Grading Rubric — 100 Points

| Criterion | Excellent | Good | Needs Improvement | Not Met | Points |
|---|---|---|---|---|---:|
| **Stock Data Collection** | Correct company data, most recent two-year period, at least 500 records, and only Date and Close retained | Mostly complete with minor date-range or cleaning issues | Incomplete period, fewer than 500 records, or unnecessary columns remain | Minimal or missing stock data | 15 |
| **Data Cleaning and Organization** | Dates and values are valid, duplicates removed, tables and filters used, and worksheets clearly organized | Data is generally clean with minor issues | Multiple formatting, duplicate, or organization problems | Data is disorganized or unusable | 10 |
| **Predictor Selection and Sources** | Three meaningful predictors are included, explained, and properly sourced | Three predictors included with minor explanation or citation gaps | Predictors are incomplete or weakly justified | Predictors or sources are missing | 10 |
| **VLOOKUP and Date Matching** | All predictors are accurately matched by Date using working exact-match VLOOKUP formulas | Most formulas work with minor unmatched records or errors | Several formula or matching errors | VLOOKUP is missing or does not work | 15 |
| **Chart Quality** | Line chart is accurate, readable, labeled, and professionally formatted | Chart is mostly correct with minor formatting issues | Chart is incomplete or difficult to interpret | Chart is missing | 5 |
| **Regression Analysis** | Regression uses the correct dependent and independent variables and includes complete output | Regression is mostly correct with minor errors | Incorrect selections or incomplete results reduce reliability | Regression is missing or unusable | 15 |
| **Interpretation and Limitations** | R-squared and p-values are accurately explained; findings and limitations are thoughtful | Interpretation is generally correct with minor gaps | Explanations show limited understanding or contain errors | Interpretation is missing | 15 |
| **Video Demonstration** | Clear 3–5 minute demonstration shows the workbook, VLOOKUP, chart, regression method, and personal understanding | Covers most required elements with minor omissions | Video is unclear, incomplete, or does not adequately demonstrate understanding | Video is missing | 10 |
| **Professionalism and Submission Completeness** | All files are submitted, clearly named, well organized, and properly cited | Submission is mostly complete with minor issues | Several required elements are missing or unclear | Submission is substantially incomplete | 5 |
|  |  |  |  | **Total** | **100** |

