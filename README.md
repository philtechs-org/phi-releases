 # phi releases

  Binary release artifacts for **phi**, the npm supply-chain firewall.

  This repo is a release container only — there is no source code here.
  The source lives at **[github.com/philtechs-org/phi](https://github.com/philtechs-org/phi)**.
  Tagged releases of phi are built by CI on the source repo and uploaded
  here so the install scripts and `phi self-update` always have a stable
  download surface.

  ## Install

  **Linux / macOS**

  ```sh
  curl -sSL https://phi.philtechs.org/install.sh | sh

  Windows (PowerShell)

  iwr -useb https://phi.philtechs.org/install.ps1 | iex

  Both scripts fetch the latest release from this repo, verify the
  sha256 against checksums.txt, and drop the phi binary on your PATH.

  Manual download

  Grab a binary directly from the Releases page (https://github.com/philtechs-org/phi-releases/releases/latest).
  Filenames follow the pattern:

  phi_<version>_<OS>_<arch>.{tar.gz,zip}

  ┌───────────────────────┬────────────────────────────────┐
  │       Platform        │             Asset              │
  ├───────────────────────┼────────────────────────────────┤
  │ Linux (x86_64)        │ phi_<ver>_Linux_x86_64.tar.gz  │
  ├───────────────────────┼────────────────────────────────┤
  │ Linux (arm64)         │ phi_<ver>_Linux_arm64.tar.gz   │
  ├───────────────────────┼────────────────────────────────┤
  │ macOS (Intel)         │ phi_<ver>_Darwin_x86_64.tar.gz │
  ├───────────────────────┼────────────────────────────────┤
  │ macOS (Apple Silicon) │ phi_<ver>_Darwin_arm64.tar.gz  │
  ├───────────────────────┼────────────────────────────────┤
  │ Windows (x86_64)      │ phi_<ver>_Windows_x86_64.zip   │
  └───────────────────────┴────────────────────────────────┘

  Verify with:

  sha256sum -c checksums.txt

  Self-update

  If you already have phi installed:

  phi self-update

  It hits this repo's GitHub API, downloads the matching asset for your
  platform, verifies the checksum, and atomically replaces the running
  binary.

  Issues, source, docs

  - Source code & issues: https://github.com/philtechs-org/phi
  - Docs & changelog: https://phi.philtechs.org
  - License: MIT (see source repo)
