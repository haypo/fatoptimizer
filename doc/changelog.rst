+++++++++
Changelog
+++++++++

fatoptimizer changelog
======================

* Version 0.3

  * Drop Python 3.4 support: Python 3.4 reached its end of life in 2019.
  * Experimental implementation of function inlining, implemented by David
    Malcolm.
  * New optimization: call pure methods of builtin types. For example,
    replace ``"abc".encode()`` with ``b'abc'``.
  * Update for fat API version 0.3, GuardBuiltins constructor changed.
  * Basic "loop unrolling" on list-comprehension, set-comprehension
    and dict-comprehension. Only if there is a single comprehension using a
    constant iterable without if.

* 2016-01-23: Version 0.2

  * Fix the function optimizer: don't specialized nested function. The
    specialization is more expensive than the speedup of optimizations.
  * Fix Config.replace(): copy logger attribute
  * get_literal() now also returns tuple literals when items are not constants
  * Adjust usage of get_literal()
  * SimplifyIterable also replaces empty dict (created a runtime) with an empty
    tuple (constant)
  * Update benchmark scripts and benchmark results in the documentation

* 2016-01-18: Version 0.1

  * Add ``fatoptimizer.pretty_dump()``
  * Add Sphinx documentation: ``doc/`` directory
  * Add benchmark scripts: ``benchmarks/`` directory
  * Update ``fatoptimizer._register()`` for the new version of the PEP 511
    (``sys.set_code_transformers()``)

* 2016-01-14: First public release, version 0.0.
