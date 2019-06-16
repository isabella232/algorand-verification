# Algorand verification

Formalization and verification of the [Algorand](https://www.algorand.com) consensus protocol using the [Coq](https://coq.inria.fr) proof assistant.

The project provides an abstract definition of the protocol as a transition system, and a complete formal proof of _safety_ for the transition system.

A statement of _liveness_ for the transition system is also provided, but the proof of liveness is currently *incomplete*.

Requirements
------------

- [`Coq 8.9`](https://coq.inria.fr/download)
- [`MathComp ssreflect 1.8.0`](https://math-comp.github.io)
- [`MathComp algebra 1.8.0`](https://math-comp.github.io)
- [`MathComp finmap 1.2.1`](https://github.com/math-comp/finmap)
- [`Interval 3.4.0`](http://coq-interval.gforge.inria.fr)
- [`Ppsimpl 8.9.0`](https://gforge.inria.fr/scm/?group_id=5430)

Building
--------

We recommend installing the dependencies of the project via
[OPAM](http://opam.ocaml.org/doc/Install.html):

```
opam repo add coq-released https://coq.inria.fr/opam/released
opam install coq.8.9.1 coq-mathcomp-ssreflect.1.8.0 \
  coq-mathcomp-algebra.1.8.0 coq-mathcomp-finmap.1.2.1 \
  coq-interval.3.4.0 coq-ppsimpl.8.9.0
```

Then, run `make` in the project root directory. This will check all the definitions and proofs.

Files
-----

All Coq vernacular files can be found under `theories`, and their content is as follows:

- `boolp.v`, `reals.v`, `Rstruct.v`, `R_util.v`: definitions and lemmas for using real numbers via MathComp and SSReflect, adapted from the [MathComp analysis project](https://github.com/math-comp/analysis)
- `fmap_ext.v`: some useful auxiliary definitions and lemmas about finite maps
- `local_state.v`: definition of Algorand local node state
- `global_state.v`: definition of Algorand global system state
- `algorand_model.v`: definition of the Algorand transition system, along with helper functions and facts
- `safety_helpers.v`: helper functions and lemmas used when proving safety of the transition system
- `quorums.v`: definitions and hypotheses about quorums of nodes
- `safety.v`: statement and complete formal proof of safety for the transition system
- `liveness.v`: statement of liveness for the transition system; note that this file contains *incomplete* (admitted) proofs

Getting Help
------------
Feel free to report GitHub issues or to contact us at: contact@runtimeverification.com
