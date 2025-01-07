// Go Into Data Tab and Select "New Table", then edit and enter script as needed //
 
Date = VAR FiscalStart = "06"

VAR STARTYEAR = "2015"

VAR ENDYEAR = "2020"

RETURN 

ADDCOLUMNS(

  CALENDAR(Date(STARTYEAR,01,01),(Date(ENDYEAR,12,31))), 

"Year" , YEAR([Date]),

"ShortYear" , VALUE(Right(YEAR([Date]),2)),

"MonthNumber" , Month([Date]),

"MonthNumberFull" , FORMAT([Date],"MM"),

"MonthFull" , FORMAT([Date],"MMMM"),

"MonthAbbr" , FORMAT ([Date],"MMM"),

"WeekNumber", WEEKNUM([Date]),

"WeekNumberFull" , Format(WEEKNUM([Date]),"00"),

"DayofMonth" , DAY([Date]),

"DayofMonthFull" , FORMAT(Day([Date]),"00"),

"DayofWeek" , WEEKDAY([Date]),

"DayofWeekFull" , FORMAT([Date],"dddd"),

"DayofWeekAbbr" , FORMAT([Date],"ddd"),

"ISODate" , YEAR([Date])&FORMAT(Day([Date]),"00")&FORMAT(Day([Date]),"00"),

"FullDate" , DAY([Date])&" "&FORMAT([Date],"MMMM")&" "&YEAR([Date]),

"QuarterFull" , "Quarter " & ROUNDDOWN(Month([Date])/4,0)+1,

"QuarterAbbr" , "Qtr " & ROUNDDOWN(Month([Date])/4,0)+1,

"Quarter" , "Q" & ROUNDDOWN(Month([Date])/4,0)+1,

"QuarterNumber" , Format(ROUNDDOWN(Month([Date])/4,0)+1,"00"),

"QuarterandYear" , "Q" & ROUNDDOWN(Month([Date])/4,0)+1 & " "& YEAR([Date]),

"MonthandYearAbbr" ,  FORMAT ([Date],"MMM") & " " & YEAR([Date]),

"QuarterandYearNumber" , YEAR([Date])&Format(ROUNDDOWN(Month([Date])/4,0)+1,"00"),

"YearandWeek", VALUE(YEAR([Date])&FORMAT(WEEKNUM([Date]),00)),

"YearandMonthNumber", VALUE((YEAR([Date])&FORMAT([Date],"MM"))),

"ISWorkDay" , IF(OR(WEEKDAY([Date])=1, WEEKDAY([Date])=7),"NO","YES"),

"CurrentMonth", IF(DATEDIFF(TODAY(),[Date],MONTH)=0,"Yes","No"),

"CurrentYear", IF(DATEDIFF(TODAY(),[Date],Year)=0,"Yes", "No"),

"MonthOffset", (DATEDIFF(TODAY(),[Date],MONTH)),

"DayOffset", (DATEDIFF(TODAY(),[Date],DAY)),

"FiscalYear", IF(FiscalStart <= FORMAT([Date],"MM"), "FY"&(YEAR([Date])+1),"FY"&YEAR([Date])),

"FiscalMonth", Value(IF(FiscalStart <= FORMAT([Date],"MM"), (Month([Date]) -FiscalStart+1), ((12-FiscalStart+1)+Month([Date])))),

"FiscalQuarter", If (Value(IF(FiscalStart <= FORMAT([Date],"MM"), (Month([Date]) -FiscalStart+1), ((12-FiscalStart+1)+Month([Date])))) < 4,"Q1", // Month 4 is start of Q1 //

    If (Value(IF(FiscalStart <= FORMAT([Date],"MM"), (Month([Date]) -FiscalStart+1), ((12-FiscalStart+1)+Month([Date])))) < 7,"Q2", // Month 7 is start of Q2 //

        If (Value(IF(FiscalStart <= FORMAT([Date],"MM"), (Month([Date]) -FiscalStart+1), ((12-FiscalStart+1)+Month([Date])))) < 10,"Q3","Q4"))) // Month 10 is start of Q3 and sets Q4 of remaining months //

)
 
