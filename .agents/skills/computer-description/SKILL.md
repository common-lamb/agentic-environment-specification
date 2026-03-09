---
name: computer-description
description: describes the setup and arrangement of the computer the agent is working within
---

# overview
- debian OS with Guix in a podman or apptainer container
- common lisp for operations
- ocicl based common lisp package management
- (asdf:load-system :some-remote-asdf-system) to obtain and load systems via ocicl
- ~/common-lisp/ to be used for symlinks to local asd files
- (ocicl-runtime-set-registry) to register new symlinks in ~/common-lisp/
- (asdf:load-system :some-local-asdf-system) to load systems via ocicl
# specification
- OS in a container, setup as full daily driver
- source setup available at: https://github.com/common-lamb/uncommon-machine
- source configuration files available at: https://github.com/common-lamb/uncommon-dotfiles
- all setup scripts 00.sh to 99.sh are available for inspection in: /opt/*.sh
- dotfiles in ~/uncommon-dotfiles managed by stow
## common lisp tools
- ocicl
- lem editor
- sbcl
- lish shell
- common lisp model context protocol
    - env: cl_mcp_port
- lem editor model context protocol
    - env: lem_mcp_port
## other tools
- encryption with age
- password store with pass-age
- local models with llama-cpp
    - env: llama_port
    - env: hf_model
- coding agent with opencode
