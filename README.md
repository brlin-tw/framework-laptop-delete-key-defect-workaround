# Framework Laptop delete key defect workaround

Workaround a manufacture defect of delete key become unresponsive on Framework Laptop keyboards before the keyboard is replaced and fixed, on Linux.

<https://gitlab.com/brlin/framework-laptop-delete-key-defect-workaround>  
[![The GitLab CI pipeline status badge of the project's `main` branch](https://gitlab.com/brlin/framework-laptop-delete-key-defect-workaround/badges/main/pipeline.svg?ignore_skipped=true "Click here to check out the comprehensive status of the GitLab CI pipelines")](https://gitlab.com/brlin/framework-laptop-delete-key-defect-workaround/-/pipelines) [![GitHub Actions workflow status badge](https://github.com/brlin-tw/framework-laptop-delete-key-defect-workaround/actions/workflows/check-potential-problems.yml/badge.svg "GitHub Actions workflow status")](https://github.com/brlin-tw/framework-laptop-delete-key-defect-workaround/actions/workflows/check-potential-problems.yml) [![pre-commit enabled badge](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "This project uses pre-commit to check potential problems")](https://pre-commit.com/) [![REUSE Specification compliance badge](https://api.reuse.software/badge/gitlab.com/brlin/framework-laptop-delete-key-defect-workaround "This project complies to the REUSE specification to decrease software licensing costs")](https://api.reuse.software/info/gitlab.com/brlin/framework-laptop-delete-key-defect-workaround)

\#framework-laptop \#delete-key \#keyd \#linux \#workaround

## Usage

Refer to the following instructions on how to workaround this defect under Linux:

1. [Install keyd](https://github.com/rvaiya/keyd?tab=readme-ov-file#installation), pre-built packages are available for many Linux distributions.
1. Install [the workaround-faulty-framework-laptop-delete-key.conf keyd configuration file](workaround-faulty-framework-laptop-delete-key.conf) to /etc/keyd _as root_.
1. Ensure the keyd daemon is running by running the following command _as root_:

    ```bash
    systemctl start keyd
    ```

1. Run the following command _as root_ to reload the configuration file if the keyd daemon is already running:

    ```bash
    keyd reload
    ```

   for Debian-based distribution the keyd command is renamed as `keyd.rvaiya` so run the following command instead:

    ```bash
    keyd.rvaiya reload
    ```

1. Done!  Now when you presses the LeftControl+Backspace key combination it will function as the alternative Delete key!

## References

The following materials are referenced during the development of this project:

* [nrp's response of Broken delete key - like literally stopped working - Community Support - Framework Community](https://community.frame.work/t/broken-delete-key-like-literally-stopped-working/37313/85)  
  Provides information regarding the keyboard defect.
* [rvaiya/keyd: A key remapping daemon for linux.](https://github.com/rvaiya/keyd)  
  The solutions that helped implmenting this workaround
* [keyd/docs/keyd.scdoc at master · rvaiya/keyd](https://github.com/rvaiya/keyd/blob/master/docs/keyd.scdoc)  
  Explains the syntax of keyd's configuration  file.
* [rightcontrol emits leftcontrol by default. · Issue #114 · rvaiya/keyd](https://github.com/rvaiya/keyd/issues/114)  
  Explains why keyd remaps right keys to their left corresponding keys by default, and how to override this behavior.

## Licensing

Unless otherwise noted([comment headers](https://reuse.software/spec-3.3/#comment-headers)/[REUSE.toml](https://reuse.software/spec-3.3/#reusetoml)), this product is licensed under [the 4.0 International version of the Creative Commons Attribution-ShareAlike License](https://creativecommons.org/licenses/by-sa/4.0/), or any of its more recent versions of your preference.

This work complies to [the REUSE Specification](https://reuse.software/spec/), refer to the [REUSE - Make licensing easy for everyone](https://reuse.software/) website for info regarding the licensing of this product.
