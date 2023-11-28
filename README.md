# Fleet Workspace (Kasm Image)

![Screenshot from 2023-03-18 12-25-23](https://user-images.githubusercontent.com/14095576/226132866-497d2a5c-17b3-4e4e-b971-9aec492841c6.png)

## Introduction

This repo provides an Immutable-Infrastructure-as-Code (IIaC) workspace for Star Trek: The Fleet (costuming fan group) based on the [Ansible based template for KASM Ubuntu Jammy Images](https://hub.docker.com/r/kasmweb/core-ubuntu-jammy) template provided by @j-simmons-phd.  The workspace is configured with the following software:

- [EmptyEpsilon](https://www.artemisspaceshipbridge.com) EE-2023.06.17 (open-source "clone" of [Artemis Spaceship Bridge Simulator](https://www.artemisspaceshipbridge.com))
- Node JS Tools
    - nodejs v17.9.0
    - npm v8.5.5 (included with nodejs)
    - npx v8.5.5 (included with nodejs)
- Utilities
    - git v2.41.0 with @capsulecorplab .gitconfig
    - [Keychain](https://www.funtoo.org/Keychain) v2.8.5
    - Vim (pre-installed) with @capsulecorplab [vimrc](https://gist.github.com/capsulecorplab/495058e7a57ed8adaed3c40c80d09739#file-vimrc)
- Web Browsers
    - firefox
- Python 3.8.x (part of the image template) with the following packages (not part of the image template)
    - pip
    - [JupyterLab](https://jupyter.org/)
    - [Jupyter Notebook](https://jupyter.org/)
    - [Voilà](https://voila.readthedocs.io/en/stable/index.html)
    - [Pint](https://pint.readthedocs.io/en/stable/)
- Artifact Generators
    - [Pandoc](https://pandoc.org/) v2.18
    - [TeX Live](https://www.tug.org/texlive/) v2022 to enable PDF support in Pandoc
    - [yq](https://mikefarah.gitbook.io/yq/) v4.20.2
    - [AsciiDoctor](https://asciidoctor.org/) v2.0.17 with PlantUML and PDF support
    - [PlantUML](https://plantuml.com/)
        - JDK v11
        - Graphviz 2.50 (built from source)
- VS Code with the following extensions (note, auto-updates are disabled)
    - [Python extension by Microsoft](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    - [Dendron](https://marketplace.visualstudio.com/items?itemName=dendron.dendron)
    - [Foam](https://marketplace.visualstudio.com/items?itemName=foam.foam-vscode)
- Artifact Generators
    - [PlantUML](https://plantuml.com/)
        - JDK v11
        - Graphviz 2.50 (built from source)
    - [AsciiDoctor](https://asciidoctor.org/) v2.0.17 with PlantUML and PDF support
    - [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- OSHW Design Tools
    - [Arduino](https://wiki-content.arduino.cc/en/software) 1.8.19
    - [PrusaSlicer](https://www.prusa3d.com/page/prusaslicer_424/) 2.7.0
    - [OpenSCAD](https://openscad.org/) 2021.01

## Requirements

1. A Bash terminal ([Ubuntu on WSL2](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#2-install-wsl) recommended for Windows users).
2. [Docker Compose](https://docs.docker.com/compose/install/) ([Docker Desktop](https://docs.docker.com/desktop/) recommended for non-Linux users)

### Additional requirements for Windows

In **Windows Features**, enable **Virtual Machine Platform** and **Windows Subsystem for Linux**

![image](https://user-images.githubusercontent.com/14095576/226184350-2b45b23b-551f-4aee-b5c9-391a20518666.png)

## Setup/Installation

From a bash terminal,

1. Clone this repo:

```bash
git clone https://github.com/startrekthefleet/fleet-workspace-image.git
```

2. Change directory into `fleet-workspace-image`:

```bash
cd fleet-workspace-image
```

3. Pull the published version of the workspace image (Note: Linux users may need to prepend this command with `sudo`):

```bash
docker-compose pull
```

Note: Alternatively, you can run `docker-compose build` to build the image locally.

## Using the image locally

Once pulled or built, the image can be run locally on port 6901 using docker-compose.

- **Starting the image locally:** Run `docker-compose up`
- **Stopping the image locally:** Use keyboard shortcut **Ctrl+C**

When running locally, the workspace can be accessed at https://localhost:6901 with
- **User:** `kasm_user`
- **Passwordd:** `password`
