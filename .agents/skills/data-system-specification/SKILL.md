---
name: data-system-specification
description: specifies the data representation system and properties. use this to understand how to categorize and place procedures and knowledge as asdf systems
---

# overview

5 distinct epistemic data types to represent knowledge and processes
these are all-together contained under leaf directories of the process taxonomic file system described in file-system-specification

# Leaf Node Specification

*Architecture, Structure, and Naming Conventions*

---

## Context

This document specifies the contents of a leaf node within a
hierarchical, self-describing process taxonomy. The taxonomy is
three levels deep. Each level narrows the domain of concern until a leaf
is reached, at which point all executable, nonderministic knowledge,
declarative knowledge, data, and artifact references are held.

The canonical taxonomy root and the leaves addressed by this document:

    business/
      coordination/
        governance/
          strategy/          <- leaf
          policy/            <- leaf
          risk/              <- leaf

Intermediate directories carry no data. They are purely organisational
namespaces. They only contain asdf systems that load their child asdf systems.
All knowledge, code, data, and references reside exclusively at the leaves.

| Level                    | Concern                                                  |
|--------------------------|----------------------------------------------------------|
| business                 | Root domain — the enterprise as a whole                  |
| coordination             | Functional cluster — how the enterprise organises itself |
| governance               | Subdomain — the governing mechanisms of coordination     |
| strategy policy risk     | Leaves — discrete process nodes holding all content      |

# 2. Design Principles

## 2.1 Self-Description

Every artefact — directory, ASDF system, source file, data file —
carries its full taxonomic address in its name. An agent inspecting
the filesystem or a running Lisp image can determine the domain,
subdomain, process, epistemic category, system identity, and package
identity of any resource from its name alone. No registry or external
index is required.

## 2.2 Uniform Loading Protocol

ASDF provides a single, uniform load protocol.
Every content item at a leaf is an ASDF system.
Parent directories contain an ASDF system that depend on the ASDF system of the children.

## 2.3 Image Navigability

Package names mirror the filesystem path using dot-separated segments. A
running Lisp image is therefore a faithful projection of the taxonomy.
Any package in the image points back unambiguously to its leaf, its
epistemic category, its ASDF system, and its source file.

## 2.4 Categorical Separation

The five leaf directories represent categorically distinct epistemic
roles. Mixing content across directories is prohibited. The separation
allows an agent to reason about the kind of knowledge a system contains
before loading or inspecting it.

## 2.5 Explicit Naming

Names are clear and explicit. Abbreviation is avoided. This follows the
Lisp tradition in which names are chosen to be read by humans and agents
alike, without reference to external documentation.

# 3. Naming Convention

The naming patterns for ASDF systems at a node is:

    <root>

    <root>.<level-1>

    <root>.<level-1>.<level-2>

    <root>.<level-1>.<level-2>.<leaf>

    <root>.<level-1>.<level-2>.<leaf>.<category>

The full naming pattern for any ASDF system at a leaf is:

    <root>.<level-1>.<level-2>.<leaf>.<category>.<system-name>.asd

For a source file within that system:

    <root>.<level-1>.<level-2>.<leaf>.<category>.<system-name>.<package-name>.lisp

Concrete example for the risk leaf:

    business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts/
    business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts.asd
    business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts.schema.lisp
    business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts.inference-rules.lisp

The category segment encodes which of the five directories the system belongs to:

| Category Segment                       | Directory                           |
|----------------------------------------|-------------------------------------|
| `.lisp-asdf-systems.`                  | lisp-asdf-systems/                  |
| `.screamer-asdf-systems.`              | screamer-asdf-systems/              |
| `.lisa-asdf-systems.`                  | lisa-asdf-systems/                  |
| `.sqlite-asdf-systems.`                | sqlite-asdf-systems/                |
| `.lisa-binary-reference-asdf-systems.` | lisa-binary-reference-asdf-systems/ |

# 4. Leaf Structure (risk leaf — canonical example)

    business/coordination/governance/risk/
    │
    ├── lisp-asdf-systems/
    │   └── business.coordination.governance.risk.lisp-asdf-systems.risk-evaluation-engine/
    │       ├── business.coordination.governance.risk.lisp-asdf-systems.risk-evaluation-engine.asd
    │       └── src/
    │           ├── business.coordination.governance.risk.lisp-asdf-systems.risk-evaluation-engine.scoring.lisp
    │           └── business.coordination.governance.risk.lisp-asdf-systems.risk-evaluation-engine.reporting.lisp
    │
    ├── screamer-asdf-systems/
    │   └── business.coordination.governance.risk.screamer-asdf-systems.risk-constraint-solver/
    │       ├── business.coordination.governance.risk.screamer-asdf-systems.risk-constraint-solver.asd
    │       └── src/
    │           └── business.coordination.governance.risk.screamer-asdf-systems.risk-constraint-solver.constraints.lisp
    │
    ├── lisa-asdf-systems/
    │   └── business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts/
    │       ├── business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts.asd
    │       └── src/
    │           ├── business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts.schema.lisp
    │           └── business.coordination.governance.risk.lisa-asdf-systems.regulatory-risk-facts.inference-rules.lisp
    │
    ├── sqlite-asdf-systems/
    │   └── business.coordination.governance.risk.sqlite-asdf-systems.risk-data/
    │       ├── business.coordination.governance.risk.sqlite-asdf-systems.risk-data.asd
    │       ├── business.coordination.governance.risk.sqlite-asdf-systems.risk-data.sqlite
    │       └── src/
    │           ├── business.coordination.governance.risk.sqlite-asdf-systems.risk-data.schema.lisp
    │           └── business.coordination.governance.risk.sqlite-asdf-systems.risk-data.data-transformations.lisp
    │
    └── lisa-binary-reference-asdf-systems/
        └── business.coordination.governance.risk.lisa-binary-reference-asdf-systems.risk-document-artifacts/
            ├── business.coordination.governance.risk.lisa-binary-reference-asdf-systems.risk-document-artifacts.asd
            └── src/
                └── business.coordination.governance.risk.lisa-binary-reference-asdf-systems.risk-document-artifacts.references.lisp

The binary artifacts store is outside the taxonomy proper but its path is located at the root:

    business/binary-artifacts-store/
    │
    ├── a3/
    │   └── a3f9c8b2d1e47f3a.../ <- hash-addressed blob
    │
    └── 7f/
        └── 7fb2341acd9e.../


# 5. Directory Descriptions

## 5.1 lisp-asdf-systems/

*Epistemic role: procedural and operational knowledge.*

Contains one or more ASDF systems implementing the executable logic of
the leaf process. Systems here answer the question of how the process
operates: what computations it performs, what transformations it
applies, what outputs it produces. LISA and Screamer are not used here;
nondeterminacy and constraint reasoning are categorically separated.
Coalton can be used here to enforce correctness in late stage refinements.

## 5.2 screamer-asdf-systems/

*Epistemic role: nondeterministic and constraint-bearing knowledge.*

Contains ASDF systems that use Screamer for nondeterministic
computation, constraint satisfaction, search spaces, and reasoning under uncertainty.
The categorical separation from `lisp-asdf-systems` signals to any
loading agent that these systems operate under different execution
semantics — backtracking, generate-and-test, constraint propagation —
that would be architecturally inappropriate to mix with deterministic
operational code.

## 5.3 lisa-asdf-systems/

*Epistemic role: declarative knowledge — facts, rules, and inference.*

Contains ASDF systems that assert facts and define production rules into
a LISA knowledge base. These systems describe what is true of the domain
and what follows from what. They do not describe how computation
proceeds; that is the role of the lisp and screamer systems. The LISA
knowledge base is populated at load time when these systems are
initialised.

## 5.4 sqlite-asdf-systems/

*Epistemic role: tabular observations, records, and reference data.*

Contains ASDF systems which refer to sqlite files holding structured data: observations, relatinships, data, registers, thresholds, reference tables, historical records, temporal data,
configuration tables. Sqlite is used because it is universally readable
without simple tooling, trivially loadable into any in-memory structure, and
fully inspectable. Files carry the full leaf prefix in their names.

## 5.5 lisa-binary-reference-asdf-systems/

*Epistemic role: referential pointers to discrete binary artifacts.*

Contains ASDF systems whose sole purpose is to assert LISA facts that
describe and locate binary artifacts held in the top-level
`binary-artifacts-store`. These systems are categorically distinct from
`lisa-asdf-systems` because they carry no domain knowledge. They are
infrastructure: a typed, queryable index into the binary store. Each
fact encodes the artifact's semantic role, its content hash, its media
type, and its store path.

# 6. Content Descriptions

## 6.1 ASDF System Files (.asd)

Each system directory contains exactly one `.asd` file bearing the full
system name. The system name in the `.asd` file is identical to the
directory name and to the filename stem, ensuring three-way consistency
that an agent can verify programmatically.

## 6.2 Lisp Source Files (src/\*.lisp)

Each source file defines one package. The filename is the full package
name with a `.lisp` extension. The in-file `defpackage` form uses the
same name. This three-way consistency — directory name, filename,
defpackage name — means the package name is sufficient to locate the
source file on disk without a registry or index.

## 6.3 LISA Fact and Rule Files

Source files within `lisa-asdf-systems` use LISA `assert` and `defrule`
forms. A schema file defines the structure of fact classes.
Inference-rule files define the production rules that fire on those
facts. The separation of schema from rules within a system is a
convention, not a requirement. All of LISA is available for use when required.

## 6.4 Binary Reference Fact Files

Source files within `lisa-binary-reference-asdf-systems` assert LISA facts of
a standard minimal reference schema. the schema may be expanded where needed.

``` commonlisp
(assert (binary-artifact
  :role   :regulatory-framework-document
  :provenance "recieved from X on date YYYY-MM-DD"
  :hash   "sha256:a3f9c8b2d1e47f3a..."
  :type   :pdf
  :path   "/binary-artifacts-store/a3/a3f9c8b2d1e47f3a..."
  :label  "Basel III Framework - BIS 2017"))
```

The hash is the canonical identity. The path is derivable from the hash.
The role and label provide semantic context queryable within the LISA
knowledge base.

## 6.5 Sqlite Data Files

Each asd system has a single sqlite file. Schema, table, index names are explicit and
descriptive. sqlite files are self-contained: they do not reference other files.
An agent or human can open any sqlite file and understand the contents by inspecting the schema alone.

# 7. Image Navigability and Back-Reference

When all systems at a leaf are loaded, by loading the node asdf system into a running Common Lisp image,
the package namespace encodes the full taxonomic provenance of every
definition. The following properties hold:

- An agent can call `list-all-packages` and group results by taxonomic
  address, reconstructing a map of which leaves and nodes are loaded and which are
  not.

- The category segment in each package name tells the agent the
  epistemic role of that package without inspecting its contents.

- The system segment names the ASDF system, allowing the agent to locate
  the `.asd` file and source tree on disk.

- The leaf segment names the filesystem directory containing the five
  category subdirectories.

No registry, manifest, or index is required. The package namespace is
the index. The taxonomy is fully recoverable from the image, and the
image is fully traceable to the taxonomy.

# 8. Agent Loading Protocol

To fully load a node or a leaf into the running image an agent performs the
following steps:

- ensure the directory hierarchy is complete and correct.
- ensure the dependency tree of ASDF systems is complete and correct
- ensure ~/common-lisp/ does not contain any broken symlinks
- ensure all asd files in the directory hierarchy are symlinked in ~/common-lisp/
- refresh the registry with (ocicl-runtime-set-registry)
- call `asdf:load-system` on the desired system
- ocicl will retrieve any remote dependencies of the leaf asdf systems, and store them in ~/ocicl/
- asdf will load dependencies according to the asdf system definitions

------------------------------------------------------------------------

*End of Specification*
