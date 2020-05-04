# trace_viz
Tool to visualize system and library calls made by a binary.

## Motivation
Outputs of strace and ltrace are a bunch of unformatted lines that don't provide much insight to the programs behavior. While using "-c" option provides a better output but is very inconsistent.\
The code is a wrapper around strace and ltrace to trace system and library calls and output a clean and formatted result to provide a better understanding of a programs functionality. 

## Bugs and Improvements
Issue: when specifying --plot option the binary is executed twice.\
Solution: can be resolved by wrapping around "strace -C" instead of calling "strace" and "strace -c" separately.

Currently output is sorted by number of calls, may add a feature to sortby other elements.

Currently using dictionaries to parse data, a better use would using pandas dataframes.

<pre>
./trace_viz: A system and library call tracer
Usage: ./trace_viz -s/l -b <binary> [-p] [-a <PID>] [-i <logfile>] [-c]
Option:
    -b, --binary
        Binary for which to trace library or system calls
    -s, --system
        Trace system calls made by the specified binary
    -l, --library
        Trace library calls made by the specified binary
    -a, --attach_process
        Attach to process with specified PID
    -i --input_log
        Give a strace/ltrace logfile generated with -tt and -T options to parse its output 
    -c --child_trace
        Trace system/library calls made by child processes, disabled by default
    -p, --plot
        Plot a graph of number of successful and error system calls, limited usage
        Use with options: -s -b
    -h, --help
        Print this help.
Requirements: python3
</pre>

