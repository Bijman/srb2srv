This shellscript has number of uses related to SRB2/SRB2Kart server. 

Mainly, the script obtains information about IP, number of players, gametype, etc. from https://old.mb.srb2.org/masterserver.php and https://srb2kart.aqua.fyi/browser/index.html, which allows user to connect directly to selected server from SRB2/SRB2Kart Master Server list. 

![srb2srv](https://user-images.githubusercontent.com/16626326/116865885-c59d4180-ac0a-11eb-84d9-481940569c5b.gif)

# Features
- Connecting directly to selected server's IP from SRB2/SRB2Kart Master Server,
- Starting server and playing, or just creating dedicated one,
- Checking if server is reachable (using jameds.org's Port Checker),
- Runs on Linux, MacOS and Windows (Git Bash).

# Dependencies
- GNU Coreutils,
- Bash or any POSIX compliant shell,
- Findutils,
- Curl,
- Gawk,
- Node.js *,
- Puppeteer *.

Additionally, Windows users need to have installed Git Bash to run this script.

\* These are only needed to obtain SRB2 Master Server list.

# Dependencies Installation
**Linux:** 
1. In terminal enter this following commands:
- Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install coreutils findutils bash curl gawk nodejs npm`,

- Arch/Arch based: `sudo pacman -S coreutils findutils bash curl gawk nodejs npm`,

- Gentoo/Gentoo based: `sudo emerge -av coreutils findutils bash curl gawk nodejs`,

2. Install Puppeteer: 
- `npm i puppeteer`.

**Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 in [HERE](https://youtu.be/SWYqp7iY_Tc?t=439),

2. Git Bash can be found on start menu,

3. Download and install Node.js from [HERE](https://nodejs.org/en/download/),

4. Enter this in Git Bash or PowerShell: `npm i puppeteer`,

5. The rest of dependencies are installed, if you followed video.

**MacOS:**
1. In terminal enter this following command:
- `brew install gawk curl node`,

2. Install Puppeteer: 
- `npm i puppeteer`.

# Installation
**Linux:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`.

3. Enter `sudo make install`, which will install to "/usr/bin" or "/usr/local/bin", if path exists, or just place script in your directory and change script's permissions to be executable: `chmod 755 srb2srv`.

**Windows:**
1. Open Git Bash,

2. Go to your user directory (usually "C:/Users/[Your username]"): `cd ~`,

3. Enter `git clone https://github.com/Bijman/srb2srv`, which is always up to date, to user directory,

4. Create directory "bin" with command: `mkdir ~/bin`,

5. Copy script to "~/bin": `cp /path/to/srb2srv ~/bin`,

6. Change script's permissions to be executable: `chmod 755 ~/bin/srb2srv`,

7. Open text editor for "~/.bash_profile": `nano ~/.bash_profile`,

8. Write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in "~/.bash_profile",

9. Check if you set properly other environment variables from "Configuration" section,

10. Enter: `source ~/.bash_profile` or restart Git Bash.

**MacOS:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`,

3. Enter `sudo make install`, which will install to "/usr/local/bin", or just place script in your directory and change script's permissions to be executable: `chmod 755 srb2srv`.

# Configuration
**If you want to connect to server in SRB2:**
1. Enter your path to SRB2 executable file ("lsdlsrb2", "srb2win.exe") in shell configuration file (for example ".bash_profile" or ".bashrc" in user's home directory): `export SRB2="/path/to/SRB2-executable-file"`,
- Note for MacOS users: SRB2 executable file should be in "/Applications/Sonic Robo Blast 2.app/Contents/MacOS/Sonic Robo Blast 2", if "Sonic Robo Blast 2.app" is installed in "Applications".

2. Set path to Node.js modules directory: `export NODE_PATH="/path/to/node_modules"`,

3. Set path to Google Chrome/Chromium sandbox (installed for example in "node_modules/puppeteer/.local-chromium/linux-869685/chrome-linux/chrome_sandbox","node_modules/puppeteer/.local-chromium/win64-869685/chrome-win/chrome.exe" or "node_modules/puppeteer/.local-chromium/mac-869685/chrome-mac/Chromium.app/Contents/MacOS/Chromium"): `export CHROME_DEVEL_SANDBOX="/path/to/chrome-sandbox"`,

**If you want start your own server in SRB2:**
1. Enter your path to SRB2 executable file ("lsdlsrb2", "srb2win.exe") in shell configuration file (for example ".bash_profile" or ".bashrc" in user's home directory): `export SRB2="/path/to/SRB2-executable-file"`,

**If you want to connect to server or start your own server in SRB2Kart:**
1. Enter your path to SRB2Kart executable file ("srb2kart.exe", "srb2kart") in shell configuration file (for example ".bash_profile" or ".bashrc" in user's home directory): `export SRB2KART="/path/to/SRB2Kart-executable-file"`.

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

     3. Check if port for SRB2/SRB2Kart server is opened:
            srb2srv --checkport

     4. Run SRB2 server and add path to addon or directory of addons:
            srb2srv --server "$HOME/addon.pk3"

     5. Run SRB2Kart dedicated server with port 5030, and add path to addon or directory of addons:
            srb2srv --dedicatedkart "$HOME/addon.pk3" --port 5030

     Exporting SRB2/SRB2Kart executable file, Google Chrome/Chromium sandbox path, Node modules path in "SRB2" or "SRB2KART", "CHROME_DEVEL_SANDBOX" and "NODE_PATH" environment variables in shell configuration file is required for script to work.
```
