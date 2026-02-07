# Helios Demo Skeleton

This skeleton serves as a basic content skeleton for demonstrating a powerful documentation site demo with the [Helios Grav Premium Theme](https://getgrav.org/premium/helios).

![](screenshot.jpg)

## Installation

1. Download latest Grav package. [Grav 1.7](https://getgrav.org/download/grav/latest) or [Grav 1.8beta](https://getgrav.org/download/grav/latest?testing)

2. Unzip the `grav-v*.zip` file.

3. Download and unzip the `grav-skeleton-helios-site.zip` Skeleton package and unzip it.

4. Replace the default `user/` folder with this skeleton's extracted folder, and rename it to `user/`

5. Launch a terminal window and navigate to the root of your Grav installation

6. Confirm you can run CLI commands by typing `bin/gpm version`.  It should output the current version of Grav you are running.

7. Install the `license-manager` plugin with the command:

    ```shell
    bin/gpm install license-manager
    ```

8. If you want to continue the process via the admin manager, install that via:

    ```shell
    bin/gpm install admin
    ```

9. When you purchased Helios, you should have received an email with a link to the [licensing.getgrav.org](https://licensing.getgrav.org).  Visit that page and download the `licences.yaml` file.

10. On your machine copy the `licenses.yaml` to the `user/data` folder.  This will allow you to install `helios` theme, as well as `svg-icons` plugin.

11. For **Helios Demo** skeleton run this command to install all the themes + plugins:

    ```shell
    bin/gpm install error codesh form page-toc shortcode-core sitemap svg-icons simplesearch
    ```

Your site should have everything it needs to replicate the **Helios Demo** skeleton site.  Please compare your local copy to the [Helios Demo Demo Site](https://demo.getgrav.org/helios).
