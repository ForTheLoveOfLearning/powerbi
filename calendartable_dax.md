## Calendar Table in M Language
### Simple table that creates a table with Columns: Date, Year, Month, Month Number and Quarter
Calendar = 
 
	ADDCOLUMNS(
    CALENDAR(Date(2013,01,01),Date(2014,12,31)), 
    "Year", Year([Date]), 
    "Month", Format([Date], "mmm"), 
    "Month Number", Month ([Date]), 
    "Quarter", Format([Date],"\QQ"))
