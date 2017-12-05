.. _documentation:

Documentation
=============

Radare2 is a large piece of software, with more than :ref:`a decade of history <history>`.
This is why we spent a lot of time to document its usages in a lot of
various forms.

The book
--------

We wrote a book about radare2, ranging from basic usage to advanced wizzardry,
so you can slap it on your reader, and enjoy it offline. If you spots some
mistakes, or want to help us to improve it, please do feel free to check the
`github repository <https://github.com/radare/radare2book>`__

- The original (and now heavily outdated) radare1 edition,
  in `PDF <http://radare.org/get/radare.pdf>`__ and `HTML <http://radare.org/r/docs.html>`__,
  if you're feeling nostalgic.
- The `current version <https://radare.gitbooks.io/radare2book/content/>`__, for the actual version of radare2
- Its `Persian translation <http://radare.org/get/radare2book-persian.pdf>`__, that might be a bit outdated

Blog
----

We're running a `blog <http://radare.today>`__ featuring various showcases,
articles, stories, examples and summaries about radare2. For example:

- An introduction to the `Visual Mode <http://radare.today/visual-mode/>`__
- `Binary diffing <http://radare.today/binary-diffing/>`__ at byte, delta and code levels
- `Rop'n'Roll <http://radare.today/ropnroll/>`__
- Writing `payloads in C <http://radare.today/payloads-in-c/>`__
- Display `types <http://radare.today/types/>`__ and format data with pf
- `Carving binaries <http://radare.today/carving-bins/>`__

Documentation
-------------

Like a lot of other free software projects, we think that the best way to understand
what a program does is to read its `source code <https://github.com/radare/radare2/>`__.
You can also check was `other people are doing <https://github.com/search?q=radare2>`__ with radare2,
and what they are :ref:`talking about <talks>`.
We generated automatic documentation for the `Vala bindings <http://radare.org/vdoc/>`__
if you're interested in using them.

Scripting
---------

Radare2 comes with a powerful API: we used ot have classic bindings, but it
required people to learn how to use radare2 twice: one for the command line,
and a second time for the bindings. So we deprecated the bindings,
and created `r2pipe <https://github.com/radare/radare2-r2pipe>`__.

It's a magical pipe where you throw radare2 commands at,
and it'll answer you their results. We wrote a `tutorial <http://radare.today/posts/javascript-in-r2/>`__
about how to use them from Nodejs and Javascript. But don't worry,
r2pipe is usable from a **large** number of languages: 
`python <https://github.com/radare/radare2-bindings/tree/master/python>`__,
`go <https://github.com/radare/radare2-bindings/tree/master/go>`__,
`php <https://github.com/radare/radare2-bindings/tree/master/php5>`__,
`ocaml <https://github.com/radare/radare2-bindings/tree/master/ocaml>`__,
`ruby <https://github.com/radare/radare2-bindings/tree/master/ruby>`__,
`awk <https://github.com/radare/radare2-bindings/tree/master/awk>`__, …
