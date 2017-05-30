# scunit

Unit test tool for smartcards

This tool sends C-APDUs to smartcards and (optionally)
verifies the received R-APDUs.

##Usage

The tool can be used in interactive mode or driven by scunit files.
While the interactive mode provides a good tool for quick
interactions with smartcards, scunit's file based mode
is the main feature.

```
./scunit -h
scunit 0.5.0
Usage: scunit [-h] [-r reader] [-p protocol] [file]
          -h: this help
   -r reader: specify to use the PCSC smart card reader named reader
              By defaults the first one found is used so you
              don't have to specify anything if you just have
              one reader
 -p protocol: protocol to use among T=0 and T=1.
              Default is to let pcsc-lite choose the protocol
        file: scunit containing APDUs
```

A simple invocation in interactive mode looks like this:
```
scunit
```

A simple invocation to execute a scunit file looks like this:

```
scunit mytest.scunit
```

##Open feature list
 * DONE: More loose syntax for R-APDUs (e.g. 'x' for don't care)
 * More powerful expressions for APDUs:
  * DONE: Multiply operator
  * Multiline APDUs ('\' at end of line)
  * Make spaces between bytes optional
 * Generation of test summaries (M of N tests passed)
 * Don't bailout when an error occurs
 * Finish implementation of 'reset' command
 * Make card selection smarter (e.g. specify ATR matcher)
 * Define grammar for test script language
 * Add packaging/installation support scripts
