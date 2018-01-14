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
