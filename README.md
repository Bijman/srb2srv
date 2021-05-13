This shellscript has number of uses related to SRB2/SRB2Kart server. 

Mainly, the script obtains information about IP, number of players, gametype, etc. from https://old.mb.srb2.org/masterserver.php and https://srb2kart.aqua.fyi/browser/index.html, which allows user to connect directly to selected server from SRB2/SRB2Kart Master Server list. 

![output](https://user-images.githubusercontent.com/16626326/116865885-c59d4180-ac0a-11eb-84d9-481940569c5b.gif)

# Features
- Connecting directly to selected server's IP from SRB2/SRB2Kart Master Server,
- Starting server and playing, or just creating dedicated one,
- Checking if server is reachable (using jameds.org's Port Checker),
- Runs on Linux and Windows (Git Bash).

# Dependencies
- GNU Coreutils,
- Bash or any POSIX compliant shell,
- Curl,
- Gawk,
- Node.js *,
- Puppeteer *.

Additionally, Windows users need to have installed Git Bash to run this script.

\* These are only needed to obtain SRB2 Master Server list.

# Dependencies Installation
**Linux:** 

1. In terminal enter this following commands:
- Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install coreutils bash curl gawk nodejs npm`,

- Arch/Arch based: `sudo pacman -S coreutils bash curl gawk nodejs npm`,

- Gentoo/Gentoo based: `sudo emerge -av coreutils bash curl gawk nodejs`,

4. Install Puppeteer: `npm i puppeteer`.

**Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 in [HERE](https://youtu.be/SWYqp7iY_Tc?t=439),

2. Git Bash can be found on start menu,

3. Download and install Node.js from [HERE](https://nodejs.org/en/download/),

4. Enter this in Git Bash or PowerShell: `npm i puppeteer`,

5. The rest of dependencies are installed, if you followed video.

# Installation
**Linux:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`.

3. Enter `sudo make install` , which will install to /usr/bin, or just place script in your directory and change script's permissions to be executable: `chmod 755 srb2srv`.

**Windows:**
1. Open Git Bash,

2. Enter `git clone https://github.com/Bijman/srb2srv`.

3. Create directory "bin" with command: `mkdir ~/bin`,

4. Copy script to ~/bin: `cp /path/to/srb2srv ~/bin`,

5. Enter: `nano ~/.bash_profile`,

6. Write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in ~/.bash_profile,

7. Check if you set properly other environment variables from "Configuration" section,

8. Enter: `source ~/.bash_profile` or restart Git Bash.

# Configuration
**If you want to connect to server in SRB2:**
1. Enter your path to SRB2 executable file (lsdlsrb2, srb2win.exe) in shell configuration file (for example .bash_profile or .bashrc in user's home directory): `export SRB2="/path/to/SRB2-executable-file"`,

2. Set path to Node.js modules directory: `export NODE_PATH="/path/to/node_modules"`,

3. Set path to Google Chrome/Chromium sandbox (installed for example in node_modules/puppeteer/.local-chromium/linux-869685/chrome-linux/chrome_sandbox or node_modules/puppeteer/.local-chromium/win64-869685/chrome-win/chrome.exe): `export CHROME_DEVEL_SANDBOX="/path/to/chrome-sandbox"`,

**If you want to run to server in SRB2:**
1. Enter your path to SRB2 executable file (lsdlsrb2, srb2win.exe) in shell configuration file (for example .bash_profile or .bashrc in user's home directory): `export SRB2="/path/to/SRB2-executable-file"`,

**If you want to connect to server or run your server in SRB2Kart:**
1. Enter your path to SRB2Kart executable file (srb2kart.exe, srb2kart) in shell configuration file (for example .bash_profile or .bashrc in user's home directory): `export SRB2KART="/path/to/SRB2Kart-executable-file"`.

**Usage (from help text):**
```
CLI for server related tools of SRB2/SRB2Kart

Usage: srb2srv [OPTION] <addon-path>
  OPTIONS:
     -h, --help                             Show this help text
     -c, --checkport                        Check if SRB2/SRB2Kart server is reachable
     -d, --dedicated      <addon-path>      Start dedicated SRB2 server
     -dk, --dedicatedkart <addon-path>      Start dedicated SRB2Kart server
     -k, --kart                             Go to SRB2Kart Master Server
     -s, --server         <addon-path>      Start SRB2 server and play
     -sk, --serverkart    <addon-path>      Start SRB2Kart server and play

  EXAMPLES:
     1. Go to SRB2Kart Master Server and connect to selected server from list:
            srb2srv

     2. Go to SRB2Kart Master Server and connect to selected server from list:
            srb2srv --kart

     3. Check if port for SRB2/SRB2Kart server is opened:
            srb2srv --checkport

     4. Run SRB2 server and add path to addon or directory of addons:
            srb2srv --server ~/addon.pk3

     Exporting SRB2/SRB2Kart executable path, Google Chrome/Chromium sandbox directory, Node modules path in "SRB2" or "SRB2KART","CHROME_DEVEL_SANDBOX" and "NODE_PATH" environment variables in shell configuration file is required for script to work.
```
