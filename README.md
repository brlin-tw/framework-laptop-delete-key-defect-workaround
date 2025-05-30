# Framework Laptop delete key defect workaround

Workaround a manufacture defect of delete key become unresponsive on Framework Laptop keyboards before the keyboard is replaced and fixed, on Linux.

<https://gitlab.com/brlin/framework-laptop-delete-key-defect-workaround>

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

1. Done!  Now when you presses the Shift+Backspace key combination it will function as the alternative Delete key!

## References

The following materials are referenced during the development of this project:

* [nrp's response of Broken delete key - like literally stopped working - Community Support - Framework Community](https://community.frame.work/t/broken-delete-key-like-literally-stopped-working/37313/85)  
  Provides information regarding the keyboard defect.
* [rvaiya/keyd: A key remapping daemon for linux.](https://github.com/rvaiya/keyd)  
  The solutions that helped implmenting this workaround
* [keyd/docs/keyd.scdoc at master · rvaiya/keyd](https://github.com/rvaiya/keyd/blob/master/docs/keyd.scdoc)  
  Explains the syntax of keyd's configuration  file.
