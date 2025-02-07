Julia v1.3 Release Notes
========================

New language features
---------------------

* Support for Unicode 12.1.0 ([#32002]).

Language changes
----------------


Multi-threading changes
-----------------------


Build system changes
--------------------


New library functions
---------------------

* `findfirst`, `findlast`, `findnext` and `findprev` now accept a character as first argument
  to search for that character in a string passed as the second argument ([#31664]).
* New `findall(pattern, string)` method where `pattern` is a string or regex ([#31834]).

Standard library changes
------------------------

* `Regex` can now be multiplied (`*`) and exponentiated (`^`), like strings ([#23422]).
* Cmd interpolation (`` `$(x::Cmd) a b c` `` where) now propagates `x`'s process flags
  (environment, flags, working directory, etc) if `x` is the first interpolant and errors
  otherwise ([#24353]).
* `IPAddr` subtypes now behave like scalars when used in broadcasting ([#32133]).

#### Libdl

* `dlopen()` can now be invoked in `do`-block syntax, similar to `open()`.

#### LinearAlgebra

* The BLAS submodule no longer exports `dot`, which conflicts with that in LinearAlgebra ([#31838]).
* `diagm` and `spdiagm` now accept optional `m,n` initial arguments to specify a size ([#31654]).

* `Hessenberg` factorizations `H` now support efficient shifted solves `(H+µI) \ b` and determinants, and use a specialized tridiagonal factorization for Hermitian matrices. There is also a new `UpperHessenberg` matrix type ([#31853]).

#### SparseArrays


#### Dates

* Fixed `repr` such that it displays `Time` as it would be entered in Julia ([#32103]).

#### Sockets

* `getipaddrs` returns IP addresses in the order provided by libuv ([#32260]).
* `getipaddr` prefers to return the first `IPv4` interface address provided by libuv ([#32260]).

#### Statistics

* `mean` now accepts both a function argument and a `dims` keyword ([#31576]).

#### Miscellaneous

* `foldr` and `mapfoldr` now work on any iterator that supports `Iterators.reverse`, not just arrays ([#31781]).

External dependencies
---------------------

Tooling Improvements
---------------------

* The `ClangSA.jl` static analysis package has been imported, which makes use of
  the clang static analyzer to validate GC invariants in Julia's C code. The analysis
  may be run using `make -C src analyzegc`.

<!--- generated by NEWS-update.jl: -->
