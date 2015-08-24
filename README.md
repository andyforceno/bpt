# Bash Package Tracker - bpt
A package tracking script for the Bash shell

Bash Package Tracker (bpt) uses the Boxoh API (www.boxoh.com) to track packages. Bpt has been tested with packages shipped within the U.S. via the following couriers: FedEx and USPS. Any package tracking limitations or errors are solely the fault of the Boxoh API. For instance, it does not return tracking information for many USPS First Class packages. Feel free to let me know which couriers work and which don't.   

    bpt - Bash Package Tracker - v1.0 (build 230815)
    Usage: bpt [OPTIONS] <tracking number> [EXTENDED] <file>

OPTIONS:

	-a | all	      	List all tracking updates for <number> or <file>	 
	-c | clean    		Remove delivered packages from <file> 
	-d=<interval>	  	Run bpt as a daemon with <interval> to check for updates
			            interval = x(s|m|h), seconds (s), minutes (m), hours (h)
			            (If blank, default from ~/.bptrc is used)
			            
    -l | -u | last		List most recent tracking update for <number> or <file>
    add 	        	Add <tracking number> to <file>
    del 		        Remove <tracking number> from <file>
    list 		        List all <tracking number> saved in <file>
EXTENDED:				

    -f		          	File to parse for tracking numbers 
				        (If blank, default from ~/.bptrc is used)

Notes:

    "-d" is equivalent to "-u" running in a loop of <interval>
    Default <file> is tracking.list 
    See ~/.bptrc for other program defaults

Examples:

    ./bpt add <tracking number>
    ./bpt -a <tracking number>
    ./bpt -a -f tracking.list
    ./bpt -u <tracking number>
    ./bpt -d=2h -f
    ./bpt clean tracking.list
    ./bpt list tracking.list

bpt - Bash Package Tracker is available under the MIT license:

The MIT License (MIT)

Copyright (c) [2015] [Andy Forceno]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
