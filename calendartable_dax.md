Calendar = 
  ADDCOLUMNS(
    CALENDAR(Date(2013,01,01),Date(2014,12,31)), 
    "Year", Year([Date]), 
    "Month", Format([Date], "mmm"), 
    "Month Number", Month ([Date]), 
    "Quarter", Format([Date],"\QQ"))
