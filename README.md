# Manufacturing Downtime Analysis  

# Overview -  

This project investigates production line efficiency to uncover key downtime causes and identify improvement areas. The analysis includes calculating operator-specific efficiency, prioritizing main downtime factors with a Pareto approach, and evaluating downtime by operator and factor using a matrix. Based on these findings, targeted recommendations were made: initiating machine adjustment training for all operators, providing specialized batch change training for Mac, and implementing preventive maintenance checks to reduce machine-related delays.

# Objective  -  

The objective of the Manufacturing Downtime Analysis at Wolf Cola is to evaluate production and downtime data from the bottling line to calculate overall line efficiency, identify key downtime factors, and assess operator performance. The analysis aims to develop actionable recommendations, including targeted training programs and maintenance practices, to improve efficiency and reduce downtime, ultimately fostering a more productive manufacturing environment.  

# Key Goals -  

1. Calculate the efficiency for a production line and break it down by operator.
2. Use a Pareto chart to identify the main factors for downtime in the production line.
3.  Use a matrix to calculate the total downtime by operator for each of the main factors you identified.


# Findings -

1. Overall Efficiency Sits at **64%**
2. Operator Charlie has the highest efficiency at **67%**.
3. The Top 5 Factors account for **80%** of the Downtime.

   > Machine adjustment
   
   > Machine failure  

   > Inventory shortage  

   > Batch change  

   > Batch coding error  

4. 3/5 main downtime factors are due to **operator error**.


# Calculations -  
```
1. In Line productivity -

   Batch Time  =( End Time - Start Time ) * 24 * 60 
   Min batch time = XLOOKUP(B2,Products!A:A,Products!D:D)

2. In Downtime factors -

   Downtime =SUM(INDEX('Line downtime'!$C$3:$N$40,,MATCH(A2,'Line downtime'!$C$2:$N$2,0)))
   Pareto   =SUM($D$2:D2)/SUM($D$2:$D$13)```

3. In Line downtime -

   Operator =XLOOKUP(A3,'Line productivity'!C2:C39,'Line productivity'!D2:D39)

4. In Dashboard -
 
   Matrix with the operators as the rows and the main downtime factors as the columns

  =SUMIFS(INDEX('Line downtime'!$C$3:$N$40,,MATCH(Dashboard!C$23,'Line downtime'!$C$2:$N$2,0)),'Line downtime'!$B$3:$B$40,Dashboard!$B25)
```

# Recommendations -  

**Machine Adjustment Training -** Implement training programs for all operators focused on machine adjustments to reduce related downtime.

**Specialized Training for Mac -** Provide special batch change training for Operator Mac to address his specific challenges.

**Preventive Maintenance -** Establish a preventive maintenance schedule for machines and ensure thorough checks to mitigate machine failures.

![Dashboard_final1](https://github.com/user-attachments/assets/00ad0f59-898f-4334-86b2-32dc57647b07)
