SHRDLU
------

This is a minimally modified version of Terry Winograd's SHRDLU code from 1972.

You can try to run this by executing clisp or some equivalent in the code 
directory, then attempting `(load "init")`.

Expect errors! This code is from 1972.

Current lines of work:
- Improve support for the behavior of MACLISP properties... the most glaring
  behavioral difference right now is that `(cdr 'foo)` for a symbol foo which 
  has a property list will actually return the property list. Additionally 
  `(get 1 'asdf)` will return nil for all properties. Ways of handling this:
   1. Let it run and handle cases as they come up (hopefully cdr is never used 
      in both the sense of "get property list" and the sense of "tail of list"
      ...
   2. Rip out every cdr and replace it with a macro.
- Macros in morpho are acting weird... they require `NOSTOP` which is defined 
  in setup and shouldn't be needed by syscom (because it is used in a function) 
  until runtime. Need insight into current macro expansions...
