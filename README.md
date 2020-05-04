# trace_viz
Tool to visualize outputs of strace and ltrace\

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
