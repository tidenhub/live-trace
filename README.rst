live-trace
==========

live-trace is a Python library to log stacktraces of a running application in a
daemon thread N times per second.  The log file can be analyzed to see
where the interpreter spends most of the time.  It is called
"live-trace" since it can be used on production systems without
noticeable performance impact.

Development
===========

# Installing for development
pip install -e git+https://github.com/guettli/live-trace.git#egg=live-trace

# Running tests
cd src/live-trace
python setup.py test

Usage
=====

Usage run-and-analyze::

    you@unix> live-trace run-and-analyze your-python-script.py

Usage run, analyze later::

    you@unix> live-trace run your-python-script.py

    The collected stacktraces will be written to $TMP/live_trace/YYYY-MM-DD....log

    Now you can analyze the collected stacktraces:

    you@unix> live-trace analyze tmp/live_trace/2017-01-09-11-23-40.log