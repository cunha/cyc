Thread-safe C library for creating cyclic rotating files
========================================================

This module creates rotating filenames based on age (`cyc_init_periodic`) or file size (`cyc_init_filesize`).  The interface is simple: (1) initialize the cyclic file handle, (2) print stuff to it, and (3) destroy the handle when you are done.

These functions use `pthread_setcancelstate` to prevent file-handling functions to work as cancellation points.  This way the calling thread can be sure that functions always return.
