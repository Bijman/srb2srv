This shell script has number of uses related to SRB2/SRB2Kart server.

Mainly, the script obtains information about IP, number of players, gametype, etc. from https://ms.srb2.org and https://srb2kart.aqua.fyi/browser/index.html, which allows user to connect directly to selected server from SRB2/SRB2Kart Master Server list.

![srb2srv](https://user-images.githubusercontent.com/16626326/134928198-1b1b3837-1da0-4f97-bb23-e533d4da3487.gif)

# Features
- Connecting directly to selected server's IP from SRB2/SRB2Kart Master Server,
- Starting server and playing, or just creating dedicated one,
- Checking if server is reachable (using [jameds.org's Port Checker](https://www.jameds.org/SRB2/port)),
- Runs on Linux, MacOS and Windows (Git Bash).

# Dependencies
- GNU Coreutils,
- Bash or any POSIX compliant shell,
- Findutils,
- Curl,
- Gawk.

Additionally, Windows users need to have installed Git Bash to run this script.

# Dependencies Installation
**Linux:** 
1. In terminal enter this following commands:
- Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install coreutils findutils bash curl gawk`,

- Arch/Arch based: `sudo pacman -S coreutils findutils bash curl gawk`,

- Gentoo/Gentoo based: `sudo emerge -av coreutils findutils bash curl gawk`.

**Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 in [HERE](https://youtu.be/SWYqp7iY_Tc?t=439),

2. Git Bash can be found on start menu,

3. The rest of dependencies are installed, if you followed video.

**MacOS:**
1. In terminal enter this following command:
- `brew install gawk curl`.

# Installation
**Linux:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`,

3. Enter `sudo make install`, which will install to "/usr/bin" or "/usr/local/bin", if path exists, or just place script in your directory and change script's permissions to be executable: `chmod 755 srb2srv`,

4. Check if you set properly environment variables from "Configuration" section,

5. Enter `source ~/.bash_profile` or restart terminal.

**Windows:**
1. Open Git Bash,

2. Go to your user directory (usually "C:/Users/[Your username]"): `cd ~`,

3. Enter `git clone https://github.com/Bijman/srb2srv`,

4. Create directory "bin" with command: `mkdir ~/bin`,

5. Copy script to "~/bin": `cp /path/to/srb2srv ~/bin` (keep in mind, that "/path/to/srb2srv" is not literal path, so type your path to srb2srv script),

6. Change script's permissions to be executable: `chmod 755 ~/bin/srb2srv`,

7. Open text editor for "~/.bash_profile": `nano ~/.bash_profile`,

8. Write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in "~/.bash_profile",

9. Check if you set properly other environment variables from "Configuration" section,

10. Enter: `source ~/.bash_profile` or restart Git Bash.

**MacOS:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`,

3. Enter `sudo make install`, which will install to "/usr/local/bin", or just place script in your directory and change script's permissions to be executable: `chmod 755 srb2srv`,

4. Check if you set properly other environment variables from "Configuration" section,

5. Enter: `source ~/.bash_profile` or restart terminal.

# Configuration
**If you want to connect to server in SRB2:**
1. Enter your path to SRB2 executable file ("lsdlsrb2", "srb2win.exe", "Sonic Robo Blast 2") or just type "flatpak" (for installed Flatpaks, Linux only) in shell configuration file (for example ".bash_profile" or ".bashrc" in user's home directory): `export SRB2="/path/to/SRB2-executable-file"` or `export SRB2="flatpak"`,
- Note for MacOS users: SRB2 executable file should be in "/Applications/Sonic Robo Blast 2.app/Contents/MacOS/Sonic Robo Blast 2", if "Sonic Robo Blast 2.app" or "Sonic Robo Blast 2 Kart.app" is installed in "Applications".

**If you want start your own server in SRB2:**
1. Enter your path to SRB2 executable file ("lsdlsrb2", "srb2win.exe", "Sonic Robo Blast 2") or just type "flatpak" (for installed Flatpaks, Linux only) in shell configuration file (for example ".bash_profile" or ".bashrc" in user's home directory): `export SRB2="/path/to/SRB2-executable-file"` or `export SRB2="flatpak"`,

**If you want to connect to server or start your own server in SRB2Kart:**
1. Enter your path to SRB2Kart executable file ("srb2kart.exe", "lsdl2srb2kart", "Sonic Robo Blast 2 Kart") or just type "flatpak" (for installed Flatpaks, Linux only) in shell configuration file (for example ".bash_profile" or ".bashrc" in user's home directory): `export SRB2KART="/path/to/SRB2Kart-executable-file"` or `export SRB2="flatpak"`,
- Note for MacOS users: SRB2Kart executable file should be in "/Applications/Sonic Robo Blast 2 Kart.app/Contents/MacOS/Sonic Robo Blast 2 Kart", if "Sonic Robo Blast 2 Kart.app" is installed in "Applications".

# Usage (from help text)
```
CLI for server related tools of SRB2/SRB2Kart

Usage: srb2srv [OPTION] <parameter>
  OPTIONS:
     -h, --help                             Show this help text.
     -c, --checkport                        Check if SRB2/SRB2Kart server is reachable.
     -d, --dedicated      <addon-path>      Start dedicated SRB2 server.
     -dk, --dedicatedkart <addon-path>      Start dedicated SRB2Kart server.
     -k, --kart                             Go to SRB2Kart Master Server.
     -p, --port           <port-number>     Specify the local UDP port to use. Works with -c, -d, -dk, -s and -sk options.
     -s, --server         <addon-path>      Start SRB2 server and play.
     -sk, --serverkart    <addon-path>      Start SRB2Kart server and play.

  EXAMPLES:
     1. Go to SRB2 Master Server and connect to selected server from list:
            srb2srv

     2. Go to SRB2Kart Master Server and connect to selected server from list:
            srb2srv --kart

     3. Check if port for SRB2/SRB2Kart server is opened (default port to be checked is 5029 without --port option):
            srb2srv --checkport --port 5030

     4. Run SRB2 server and add path to addon or directory of addons:
            srb2srv --server "$HOME/addon.pk3"

     5. Run SRB2Kart dedicated server with port 5030, and add path to addon or directory of addons:
            srb2srv --dedicatedkart "$HOME/addon.pk3" --port 5030

  NOTES:
     Exporting SRB2/SRB2Kart executable file ("lsdlsrb2", "srb2win.exe", "Sonic Robo Blast 2", "lsdl2srb2kart", "srb2kart.exe", "Sonic Robo Blast 2 Kart") path or "flatpak" (for installed Flatpaks, Linux only) in "SRB2" or "SRB2KART" environment variable to shell configuration file (for example in ".bashrc" or ".bash_profile") is required for script to work.
     Here are a few examples:
       SRB2
         1. Linux:
            - export SRB2="$HOME/Games/SRB2/lsdlsrb2",
            - export SRB2="flatpak".
         2. Windows:
            - export SRB2="$HOME/Games/SRB2/srb2win.exe".
         3. MacOS:
            - export SRB2="/Applications/Sonic Robo Blast 2.app/Contents/MacOS/Sonic Robo Blast 2".
       SRB2Kart
         1. Linux:
            - export SRB2KART="$HOME/Games/SRB2Kart/lsdl2srb2kart",
            - export SRB2KART="flatpak".
         2. Windows:
            - export SRB2KART="$HOME/Games/SRB2Kart/srb2kart.exe".
         3. MacOS:
            - export SRB2KART="/Applications/Sonic Robo Blast 2 Kart.app/Contents/MacOS/Sonic Robo Blast 2 Kart".
```
