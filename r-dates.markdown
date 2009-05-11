Dates done right 
================

review existing date time classes in R: xts, its, ti, chron, POSIXct, POSIXlt

integer double, stores number of milliseconds since 01-01-1970

instant:   fixed point in time
partial:   partial specification of time
interval:  two instants
duration:  
period:    hours(2) days(3) weeks(6) months(1) years(5)

- need a grid showing which operations are meaningful, -, + and *, including raw numbers, and what type of object they result in

  * period + period = period
  * period * number = period
  * period + partial = partial ?
  
  * instant +/- period = instant
  * instant + partial = instant
  * instant - instant = duration
  
  * duration / period = number?

dt + hours(5)
dt1 - dt2 
dt + partial(tz = "America/New York")
dt + partial(month = 1, day = 1) = dt(month) <- 1; dt(day) <- 1
day_of_year, day_of_month, day_of_week vs. yday, mday, wday ?
hour_of_day, etc.

(Visualise time zone data?) 

Also important to have good methods for automatically selecting pretty breaks for time data

Non-linear date scales:
  * compress history, expand current
  * remove weekends etc.
