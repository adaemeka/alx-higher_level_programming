There are (at least) two distinguishable kinds of errors in python:
syntax errors and exceptions.

Syntax Errors
Syntax errors, also known as parsing errors,
are perhaps the most common kind of complaint
you get while you are still learning Python:
The parser repeats the offending line and displays
a little ‘arrow’ pointing at the earliest point in the line
where the error was detected.
The error is caused by (or at least detected at)
the token preceding the arrow:

Exceptions
Even if a statement or expression is syntactically correct,
it may cause an error when an attempt is made to execute it.
Errors detected during execution are called exceptions
and are not unconditionally fatal:
you will soon learn how to handle them in Python programs.
Most exceptions are not handled by programs.
