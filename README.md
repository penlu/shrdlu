SHRDLU
------

This is a minimally modified version of Terry Winograd's SHRDLU code from 1972.

You can try to run this by executing clisp or some equivalent in the code 
directory, then attempting `(load "init")`.

Expect errors! This code is from 1972.

Current line of work:
- Improve support for the behavior of MACLISP properties... the most glaring
  behavioral difference right now is that `(cdr 'foo)` for a symbol foo which 
  has a property list will actually return the property list. Additionally 
  `(get 1 'asdf)` will return nil for all properties.
