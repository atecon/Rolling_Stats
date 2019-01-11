================================
"RollingStats"  -- Gretl package
================================


Public functions:
*****************
`rolling_ts()`: Rolling Univariate Time-series Statistics
-------------
+ This function allows the user to compute specific statistics
in either a 'rolling' (fixed, shifting window through time) or 'recursive'
(expanding window through time) manner.
+ In principle all -- both built-in as well as user-defined functions (UDF)
-- can be called which have a scalar value as its outcome.

`rolling_ts_list()`: Rolling Univariate Time-series Statistics
-------------------
+ This function is similar to rolling_ts() but mainly for UDFs which return
a matrices object which can comprise multiple matrices
+ Also this function allows the user to supply a list of series instead of a single series

`rvec2series()`:
--------------
+ Transforms the resulting vector from rolling_ts() into a series

`rolling_ts_gui()`:
---------------
+ Access rolling_ts() and rvec2series() through the GUI

-----------------
`rolling_ts()`:
-----------------
INPUT:
series y: 		series which is used for computing some statistics
string op:		string, name of the function you want to call
int wsize[1::2]:	integer, size of the moving window (default 2 periods)
bool recursive[0]:	0: rolling-window (default), 1: recursive (expanding) window

OUTPUT: R by 1 matrix
+ Matrix includes the computed statistics for each of the R windows

-------------------
`rolling_ts_list()`:
-------------------
INPUT:
list y: 		list which is used for computing some statistics
string op:		string, name of the function you want to call
int wsize[1::2]:	integer, size of the moving window (default 2 periods)
bool recursive[0]:	0: rolling-window (default), 1: recursive (expanding) window

OUTPUT: a matrices object holding some R by 1 matrices
+ Details depend on the user-defined funtion

-----------------
`rvec2series()`:
-----------------
INPUT:
series y: 		series which is used for computing some statistics
matrix ret:		matrix, R by 1 vector comprising the computed statistics
int wsize[1::2]:	integer, size of the moving window (default 2 periods)
bool recursive[0]:	0: rolling-window (default), 1: recursive (expanding) window

OUTPUT: series
+ Series of rolling/ recursively computed statistics based in 'y'
correctly aligned with time

-----------------
`rolling_ts_gui()`:
-----------------
INPUT:
series y: 		series which is used for computing some statistics
string op:		string, name of the function you want to call
int wsize[1::2]:	integer, size of the moving window (default 2 periods)
bool recursive[0]:	0: rolling-window (default), 1: recursive (expanding) window

OUTPUT: series
+ Series of rolling/ recursively computed statistics based in 'y'
correctly aligned with time
