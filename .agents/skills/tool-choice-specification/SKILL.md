---
name: tool-choice-specification
description: preferred tools and software constraints
---

# overview

this is the list to consult when choosing software and selecting among asdf systems

# specification

functional programming patterns are preferred but not mandatory
where critical correctness is required, use coalton for typechecking

we use ocicl to obtain asdf systems from the internet
see this list for availability: https://raw.githubusercontent.com/ocicl/request-system-additions-here/main/all-ocicl-systems.txt

# common lisp systems

common lisp model context protocol: https://github.com/cl-ai-project/cl-mcp
editor: https://github.com/lem-project/lem
lem model context protocol: built in

build system: https://common-lisp.net/project/asdf/
software distribution: https://github.com/ocicl/ocicl
tests: https://github.com/melisgl/try
documentation: https://github.com/melisgl/mgl-pax
database interaction: https://github.com/fukamachi/cl-dbi
forward chaining expert system: https://github.com/youngde811/Lisa
non deterministic programming: https://github.com/nikodemus/screamer
asdf templates: https://github.com/fukamachi/cl-project
repl introspection: https://github.com/m-n/repl-utilities

stats and visualization: https://github.com/lisp-stat
machine learning: https://github.com/melisgl/mgl
matrix math: https://github.com/quil-lang/magicl

algebraic data types: https://github.com/coalton-lang/coalton/
parallel processing: https://github.com/sharplispers/lparallel
memoization: https://github.com/AccelerationNet/function-cache
data transformation: https://github.com/fosskers/cl-transducers/
data structures: https://common-lisp.net/project/fset
data structures: https://github.com/slburson/misc-extensions
actors pattern: https://github.com/mdbergmann/cl-gserver

utilities: https://common-lisp.net/project/alexandria/
utilities: https://github.com/ruricolist/serapeum/
iteration: https://common-lisp.net/project/iterate/
serialization: https://github.com/ajberkley/cl-binary-store
time: https://common-lisp.net/project/local-time/
regexes: http://weitz.de/cl-ppcre/
strings: https://github.com/vindarel/cl-str

websites: https://github.com/rabbibotton/clog
css styling: https://codeberg.org/shinmera/LASS
http client: https://github.com/fukamachi/dexador
payment: https://github.com/boogsbunny/stripe

machine introspection: https://codeberg.org/shinmera/machine-state/
logging: https://github.com/sharplispers/log4cl/
infrastructure: https://spwhitton.name/tech/code/consfigurator/
deployment: https://codeberg.org/shinmera/deploy

files and dirs: https://common-lisp.net/project/asdf/uiop.html (never osicat!)
file system search: https://github.com/lisp-maintainers/file-finder/
pathnames: https://codeberg.org/shinmera/pathname-utils
filesystem: https://codeberg.org/shinmera/filesystem-utils
file attributes: https://codeberg.org/shinmera/file-attributes

where not specified, choose mainstream common lisp systems with good documentation

# non common lisp packages

design process inspiration: https://github.com/nathanodle/spark
database: sqlite
tunneling: cloudflare
networking: tailscale / headscale
encryption: age
containers: podman
payment: stripe
