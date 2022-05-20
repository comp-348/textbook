# Installing The Languages

Here's what we're going to install:

- A Unix development environment
- The Steel Bank Common Lisp compiler
- The SWI-Prolog compiler
- The GNU C compiler
- The Python compiler
- The Visual Studio Code editor, with language support

The installation process will rely heavily on the _terminal_, or text interface
to your computer. If you're not too familiar with it, don't worry about it too
much for now, we'll setup in-editor tools for you to use too. If you do want to
learn or brush up on your unix terminal knowledge here's a [terminal tutorial][terminal-tutorial].

[terminal-tutorial]: https://ubuntu.com/tutorials/command-line-for-beginners

```{tip}
If this is your first time installing development software, it's worth pointing
out that "close doesn't count": trying to proceed past an error usually just
leads to worse errors, and sadness. That's because we're installing a kind of
tower of software, with each level of the tower building on the previous. If
you're not building on a solid foundation, the whole thing might collapse. The
good news is that if you do get an error, you're probably not alone. A quick
google search will often turn up solutions that others have discovered. Of
course, do think critically about suggestions made by random strangers on the
internet.

Don't forget to ask for help too if Google doesn't help you get unstuck!
```

Let's get started!

## Unix Development Environment

**First, upgrade your OS.** If you've been intending to make any major OS
upgrades, do them now. Otherwise when you do get around to upgrading, you might
have to repeat some or all of this installation process. Better to get it out of
the way beforehand.

**Linux.** If you're already running Linux, you're done with this step. Move to
the next step below.

**Mac.** Beneath the surface, macOS is already a Unix-based OS. But you're going
to need some developer tools and a Unix package manager. We're going to use the
[Homebrew][homebrew] tool. Make sure to run the update command before continuing
with these instructions.

[homebrew]: https://brew.sh/

**Windows.** Unix development in Windows 10 is made possible by the Windows
Subsystem for Linux (WSL). Follow [Microsoft's install instructions for
WSL][wsl]. Here are a few notes on Microsoft's instructions:

- From the perspective of this textbook and class, it doesn't matter whether
  you join Windows Insider.

- WSL2 is preferred over WSL1 due to performance and functionality improvements,
  so install WSL2 if you can (if you can't, WSL1 is perfectly fine).

- To open Windows PowerShell as Administrator, click Start, type PowerShell,
  and it should come up as the best match. Click "Run as Administrator",
  and click Yes to allow changes.

- To use WSL2 (rather than WSL1) you might need to enable virtualization in your
  machine's BIOS; some laptop manufacturers disable it before shipping machines
  from the factory. The instructions for that are dependent on the manufacturer
  of your machine. Try googling "enable virtualization <manufacturer> <model>",
  substituting for the manufacturer and model of your machine. This
  [Red Hat Linux][rh-virt] page might also help.

- These instructions assume that you install Ubuntu (20.04) as the Linux
  distribution from the Microsoft Store. In principle other distributions should
  work, but might require different commands from this point forward.

- You will be prompted to create a Unix username and password. You can use any
  username and password you wish. It has no bearing on your Windows username and
  password (though you are free to re-use those). Do not put a space in your
  username. Do not forget your password. You will need it in the future.

- To enable copy-and-paste, click on the icon on the top left of the shell
  window, click Properties, and make sure “Use Ctrl+Shift+C/V as Copy/Paste” is
  checked. Now Ctrl+Shift+C will copy and Ctrl+Shift+V will paste into the
  terminal. Note that you have to include Shift as part of that keystroke.

[wsl]: https://docs.microsoft.com/en-us/windows/wsl/install-manual
[rh-virt]: https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/virtualization_administration_guide/sect-virtualization-troubleshooting-enabling_intel_vt_and_amd_v_virtualization_hardware_extensions_in_bios

When you've finished installing WSL, open the Ubuntu app. You will be at
the _Bash prompt_, which looks something like this:

```console
user@machine:$
```

Run the following command to update the _APT package manager_, which is what
helps to install Unix packages:

```console
sudo apt update
```

You will be prompted for the Unix password you chose. The prefix `sudo` means to
run the command as the administrator, aka "super user". In other words, do this
command as super user, hence, "sudo".

```{warning}
Running commands with `sudo` is potentially dangerous and should not be done
lightly. Do not get into the habit of putting `sudo` in front of commands, and
do not randomly try it without reason.
```

Now run this command to upgrade all the APT software packages:

```console
sudo apt upgrade -y
```

WSL has its own filesystem that is distinct from the Windows filesystem, though
there are ways to access each from the other. This is a potentially tricky
concept to master.

- When you launch Ubuntu and get the $ prompt, you are in the WSL filesystem.
  Your home directory there is named `~`, which is a built-in alias for
  `/home/your_user_name`.

- When you use Windows, you are in the Windows filesystem. [Microsoft issued one
  hard-and-fast rule][wsl1-fs]: "Do not under any circumstances access
  [WSL filesystem] files using Windows." You can corrupt the files.

[wsl1-fs]: https://devblogs.microsoft.com/commandline/do-not-change-linux-files-using-windows-apps-and-tools/

We recommend storing your development work in the WSL filesystem, not the
Windows filesystem.

## Installing Compilers

**Linux.**

- AUR: `yay install sbcl swi-prolog vscode ruby`
- Apt:
  ```console
  sudo apt install sbcl swi-prolog ruby
  curl -OL https://go.microsoft.com/fwlink/?LinkID=760868 | sudo apt install
  ```

**Mac.** Run this command from your terminal:

```console
brew install sbcl swi-prolog visual-studio-code
```

MacOS comes with GCC and Ruby pre-installed.

**Windows.** Run this command from Ubuntu:

```console
sudo apt install sbcl swi-prolog ruby
```

## Verifying the Installations

You should now have everything installed! To verify this, we're going to run a couple commands:

```console
sbcl --help
swipl --help
ruby --help
gcc --help
code --help
```

If any of these give you an error, try going back up to read the installation instructions and try again.

## Visual Studio Code

Visual Studio Code is a great choice of editor for any of these languages.
We're going to install a couple of things to get VS Code working with
all of these languages.

- **Windows only:** Install the `Remote - WSL` extension. Second, open a WSL
  window by using the command `Remote-WSL: New Window` or by running `code .` in
  Ubuntu. Either way, make sure you see the green "WSL" indicator in the
  bottom-left of the VS Code window. Follow the rest of the instructions in that
  window.

- **Mac only:** Open the Command Palette and type `shell command` to find the
  `Shell Command: Install 'code' command in PATH` command. Run it. Then close
  any open terminals to let the new path settings take effect.

- **For everyone:** In the extensions pane, search for and install the following
  extensions:

  - Alive: Average Lisp VSCode Environment by Rich Heller
  - VSC-Prolog: Support for Prolog language by arthurwang
  - C/C++: C/C++ IntelliSense, debugging, and code browsing. by Microsoft
  - Ruby: Ruby language support and debugging for Visual Studio Code by Peng Lv

  **Windows only:**
  make sure you install the extensions with the button that says "Install on WSL:
  ...", not with a button that says only "Install". The latter will not
  work.

  Not that we're not installing any Java extensions here. I assume that most of you
  are already comfortable with Eclispe or IntelliJ and would rather use one of those.
  If not, then the Microsoft `Extension Pack for Java` will provide Java support in
  vscode.

## VS Code Settings

We recommend tweaking a few editor settings. Open the user settings JSON file by
(i) going to View → Command Palette, (ii) typing “settings json”, and (iii)
selecting Open Settings (JSON). Copy and paste these settings into the window:

```json
{
  "editor.tabSize": 2,
  "editor.rulers": [80],
  "editor.formatOnSave": true
}
```

Save the file and close the tab.

## Using VS Code Collaboratively

VS Code's [Live Share][liveshare] extension makes it easy and fun to collaborate
on code with other humans. You can edit code together like collaborating inside
a Google Doc. It even supports a shared voice channel, so there's no need to
spin up a separate Zoom call. To install Live Share:

- Open the Extensions page in VS Code. Search for "Live Share Extension Pack".
  Install it.

- The first time you use Live Share, you will be prompted to login. If you are a
  Cornell student, choose to login with your Microsoft account, not Github.
  Enter your Cornell NetID email, e.g., your_netid@cornell.edu. That will take
  you to Cornell's login site. Use the password associated with your NetID.

To collaborate with Live Share:

- The _host_ starts the Live Share session. That generates a URL. Send the
  URL to the _guests_ however you like (DM, email, etc.).

- The guest puts that URL into a browser or directly into VS Code, and connects
  to the shared programming session.

[liveshare]: https://code.visualstudio.com/learn/collaboration/live-share
