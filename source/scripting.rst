.. _scripting:

Scripting
=========

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

Examples
--------

Python
^^^^^^

.. code-block:: python

  import r2pipe

  r2 = r2pipe.open("/bin/ls")
  r2.cmd('aa')
  print(r2.cmd("afl"))
  print(r2.cmdj("aflj"))  # evaluates JSONs and returns an object
  r2.quit()

Haskell
^^^^^^^

.. code-block:: haskell

  import R2pipe
  import qualified Data.ByteString.Lazy as L

  showMainFunction ctx = do
      cmd ctx "s main"
      L.putStr =<< cmd ctx "pD `fl $$`"

  main = do
      -- Run r2 locally
      open "/bin/ls" >>= showMainFunction
      -- Connect to r2 via HTTP (e.g. if "r2 -qc=h /bin/ls" is running)
      open "http://127.0.0.1:9090" >>= showMainFunction

NodeJS
^^^^^^

.. code-block:: javascript

  var r2pipe = require('r2pipe');

  function doStuff (err, r2p) {
    if (!err) {
      console.log (r2p.cmdj('ij'));
    } else  {
      console.log(`Error: ${err.message}`)
    }
    r2p.quit();
  }

  /* rlang r2pipe script ( r2 -qi foo.js /bin/ls ) */
  r2pipe.open (doStuff);

  r2pipe.open ('/bin/ls', doStuff);

  r2pipe.open ('http://cloud.radare.org/cmd/', doStuff);
