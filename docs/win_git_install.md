# Windows installation

1. Download the [Git for Windows installer](https://git-scm.com/download/win).

2. Run the installer and follow the steps below:

   * Click on `Next` to get through the license screen.

   * Click on `Next` to accept the default installation path of
   `C:\Program Files\Git`.

   * On the Select Components screen, you may wish to check the box to
   create Desktop icons.  Please do not change the other selections.
   Click `Next`.

   * Click on `Next` to accept `Git` as the name of the Start Menu folder.

   * On the **Choosing the default edit used by Git** panel, please select

   * from the dropdown menu **Use the nano editor by default** -- you may
   need to scroll _up_ in the list to find it.  Click on `Next`.

   * Ensure that **Git from the command line and also from 3rd-party
   software** is selected and click on `Next`. (If you don't do this Git
   Bash will not work properly, requiring you to remove the Git Bash
   installation, re-run the installer and to select the **Git from the
   command line and also from 3rd-party software** option.)

   * Keep the OpenSSH option if it gives you an option to change that.

   * Ensure that **Use the native Windows Secure Channel library** is
   selected and click on `Next`.

   * Ensure that **Checkout Windows-style, commit Unix-style line endings**
   is selected and click on `Next`.

   * Ensure that **Use Windows' default console window** is selected and
   click on `Next`.

   * Choose the **Default behavior of git pull** to be **Default (fast-forward
   or merge)**.

   * From **Choose a credential manager**, choose **Git Credential Manager
   Core**.

   * Ensure that **Enable file system caching** is selected

   * Do _NOT_ enable experimental support for pseudo consoles.  Clicking
   `Next` here should start the installation with no further selection
   screens.

   * This should bring you to a screen where you can click `Finish`.
   Unless you are really interested, you should uncheck the box to view
   the release notes.

3. If your `HOME` environment variable is not set (or you don't know
   what this is), then

    * Open command prompt (Open Start Menu then type cmd and press [Enter])

    * Type the following line into the command prompt window exactly as shown:
    ```
    setx HOME "%USERPROFILE%"
    ```

    * Press `Enter`, you should see output that indicates
    ```
    SUCCESS: Specified value was saved.
    ```

    * Quit command prompt by typing `exit` then pressing `Enter`

Completing those steps will provide you with both Git and Bash in the Git
Bash program.
