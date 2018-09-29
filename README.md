# changeOfSeason
Using table tbl_sun_loc_site of database named LocalWeather, determines when the season changes from: winter to spring (geocentric right ascension = 0 hours (i.e. modulo 24); spring to summer (geocentric right ascension = 6 hours); summer to autumn (geocentric right ascension =12 hours); autumn to winter (geocentric right ascension =18 hours)
 /Users/cjc/Library/Developer/Xcode/DerivedData/Build/Products/Debug/changeOfSeason --help
Starting execution of Program:
/Users/cjc/Library/Developer/Xcode/DerivedData/Build/Products/Debug/changeOfSeasonThe intent of program /Users/cjc/Library/Developer/Xcode/DerivedData/Build/Products/Debug/changeOfSeason is to determine when season change occurs. This program uses these command line
switches to customize the results:
The very first item on the command line should be a 0 or a 1. 0, the **default** value, informs the program that we should
use the prototype SQL to generate customized SQL for determining when spring occurs; 1 informs this program that we should
use the prototype to generate customized SQL for determining when the other three seasons occur. Following this single digit
(0 or 1) these switch-introduce commmand line parameters can appear in any order:
--date <val> or -d <val>:   provides the date of interest where <val> is like YYYY-MM-DD
--num <val> or -n <val>:    provides the number of rows, both before and after, the field of interest. Where <val> is an
unsigned, positive, number.
--field <val> or -f <val>:      field of interest. Only valid values are one of: `topocentricra`, `azimuth`, `geocentricra`,
	`era`, `last`, or `gast`. Nothing else will do! [default=>geocentricra]
--beep or -b: Beep the operator/user
--siteid <val> or -s <val>: provides the id of the site of interest. <val> is a positive number [default=>9]
--readFile <r_filename> or -r <r_filename>: [TBD] provides the name of the file from which we will read a prototype SQL. 
--rightAscension <ra> or -r <ra> :provides the geocentric right ascension value that the defines the season:
	spring=>24
	summer=>6;
	fall=>12;
	Winter=>18.
--writeFile <w_filename> or -w <w_filename> : [TBD] Write to file <w_filename> if so desired. 
--debug1 or -1: --debug1 (-1) is for debuging main.cpp 
--debug2 or -2: --debug2 (-2) is for debuging databaseConnectAndExecuteSQL.cpp/hpp
--debug3 or -3: --debug3 (-3) is for debuging customize_proototype_sql.cpp/hpp
--debug4 or -4: --debug4 (-4) is for debuging ChebyshevChunk.cpp/hpp 
--debug5 or -5: --debug5 (-5) is for debuging InterPolation.cpp/hpp
--debug6 or -6: --debug6 (-6) is for debuging makeConnectionString.cpp/iobuf.h/IoBuf.hpp 
--debug7 or -7: --debug7 (-7) is for debuging julianToGregorian.cpp/hpp 
--help or -h: Shows this help message
The absence of date, num, field, or siteid parameters will mean that default values will be used instead:
	 absence of --date or -d will mean that the current date will be used;
	 absence of the --num or -n parameter means that we will default to using 5 for this parameter:
	 absence of the --siteid or -s parameter means that we will default ot using 9 for the siteid
	 absence of the --field or -f parameter means that we will default to using geocentricra as the field.
