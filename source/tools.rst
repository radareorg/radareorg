.. _tools:

Tools
=====

Since radare2 is completely extensible, some people have come up with interesting projects
based or around it. Here are, in our opinion, the most significant/advanced/useful ones.

r2frida
-------

Maybe you've heard of the **amazing** `frida <https://www.frida.re/>`_ project,
by `oleavr <https://twitter.com/oleavr>`__,
a dynamic instrumentation toolkit for developers, reverse-engineers, and security researchers,
written in javascript and super easy to use?

Then we have good news: there is `r2frida <https://github.com/nowsecure/r2frida>`__,
a plugin to combine them both! It was presented at the :ref:`r2con 2017 <r2con_2017>`
(you can check the slides `here <https://slides.com/oleavr/r2frida/>`__.

To use it, you can either specify a pid, a process name, or a binary:

::

  $ r2 frida://1234
  $ r2 frida://Twitter
  $ r2 frida://"/bin/ls -al"

This will make radare2 use frida as a backend.

r2 webui
--------

Radare2 comes with a web interface, that can be launched via ``r2 -c=H /bin/ls``,
and it looks like this:

.. image:: _static/webui.png
  :alt: webui screenshot
  :scale: 75 %
  :align: center

jupyter-radare2
---------------

A simple radare2 `Jupyter <https://jupyter.org/>`__ kernel,
by `guedou <https://twitter.com/guedou>`__, that can be used to make
interactive radare2 tutorials, or take advanced notes.
You can get it `here <https://github.com/guedou/jupyter-radare2>`__.

::

  $ jupyter console --kernel radare2
  Jupyter console 5.2.0

  In [1]: o /bin/ls
  9
  In [2]: afl

  In [3]: afl~main

  In [4]: pd 5
  ;-- entry0:
    0x00005430      31ed           xor ebp, ebp
    0x00005432      4989d1         mov r9, rdx
    0x00005435      5e             pop rsi
    0x00005436      4889e2         mov rdx, rsp
    0x00005439      4883e4f0       and rsp, 0xfffffffffffffff0
  In [5]:                                                                                                                                               
  Do you really want to exit ([y]/n)? y
  Shutting down kernel


It looks like this:

.. image:: _static/jupyter_radare2.png
  :alt: jupyter notebook for radare2
  :scale: 30 %
  :align: center
  :target: https://github.com/guedou/jupyter-radare2


