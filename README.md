# POWEBI--Time-intelligence-to-compare-to-previous-year

# Using Time Intelligence to Compare Previous Year Revenue

This project demonstrates how time intelligence functions in DAX are used in Power BI to compare current revenue with previous-year performance using the Adventure Works dataset.

The focus is not on complex visuals, but on understanding how measures behave when the time context changes.

## Project Overview

In this exercise, I created revenue-based measures that allow year-over-year analysis.  
The goal was to see how business performance changes over time using the same calculation logic but a different date context.

This approach reflects how real business reports are built in Power BI.

## Revenue Measure

Revenue is not directly available in the dataset, so it must be calculated.

The revenue measure multiplies unit price by quantity at the row level and then aggregates the result.  
Using `SUMX` ensures the calculation respects filters applied in the report, such as year or month.

The measure is formatted as currency for clear business interpretation.

## Previous Year Revenue (Revenue PY)

At this stage, the calculation itself does not change.  
What changes is *when* the calculation is evaluated.

The `SAMEPERIODLASTYEAR` function shifts the date context to the same period in the previous year.  
`CALCULATE` applies this new context to the existing Revenue measure.

This produces the previous year’s revenue for the same months being viewed in the report.

## Year-over-Year Change

Once current revenue and previous-year revenue are available, the comparison becomes straightforward.

The YoY percentage measure calculates the difference between the two values and expresses it relative to the previous year.  
`DIVIDE` is used to safely handle cases where previous-year values may be missing.

The result clearly shows growth or decline over time.

## Report View

A matrix visual is used to display the measures by year and month.  
Placing Revenue, Revenue PY, and Revenue YoY % side by side makes trends easy to observe.

This layout mirrors how time-based analysis is commonly presented in business dashboards.

## Key Takeaway

Time intelligence in DAX is about controlling date context, not rewriting calculations.  
By keeping the logic consistent and shifting the time frame, meaningful comparisons can be created with clean, readable measures.



