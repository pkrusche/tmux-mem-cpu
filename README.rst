====================================================
               tmux-mem-cpu
====================================================
----------------------------------------------------
CPU and RAM monitor for use with tmux_
----------------------------------------------------



Description
===========


A simple, lightweight program provided for system monitoring in the *status*
line of **tmux**.

The memory monitor displays the used and available memory.

The CPU usage monitor outputs a percent CPU usage over all processors.

It also displays a textual bar graph of the current percent usage.

Screenshot
==========

.. image:: https://github.com/mandre/tmux-mem-cpu/raw/master/screenshot.png

Example output::

  1119/3819MB ▄  76.5% ▇

   ^    ^     ^    ^   ^
   |    |     |    |   |
   1    2     3    4   5

1. Currently used memory.
2. Available memory.
3. Memory usage bar graph.
4. CPU usage percentage.
5. CPU usage bar graph.


Installation
============


Dependencies
------------

Building
~~~~~~~~

* >= cmake_ -2.6
* C++ compiler (e.g. gcc/g++)


Download
--------

There are links to the source code at the `project homepage`_.


Build
-----

::

  cd <source dir>
  cmake .
  make


Install
-------

::

  su -
  make install
  logout



Configuring tmux_
=======================


Edit ``$HOME/.tmux.conf`` to display the program's output in *status-left* or
*status-right*.  For example::

  set -g status-interval 2
  set -g status-left "#S #(tmux-mem-cpu 2 'fg=blue,bg=black,bright')#[default]"

Note that the first argument to `tmux-mem-cpu` should be the same number
of seconds that *status-interval* is set at.

An optional second argument is the default text foreground color.

Authors
=======

* Matt McCormick (thewtex) <matt@mmmccormick.com>
* Martin André <martin.andre@gmail.com>


.. _tmux: http://tmux.sourceforge.net/
.. _cmake: http://www.cmake.org
.. _`project homepage`: http://github.com/mandre/tmux-mem-cpu
