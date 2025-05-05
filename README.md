This shell script has number of uses related to SRB2/SRB2Classic/SRB2 Legacy/Ring Racers server.

Mainly, the script obtains information about IP, number of players, gametype, etc. from https://ms.srb2.org and https://ms.kartkrew.org, which allows user to connect directly to selected server from SRB2/SRB2Classic/SRB2 Legacy/Ring Racers Master Server list.

![srb2srv](https://user-images.githubusercontent.com/16626326/134928198-1b1b3837-1da0-4f97-bb23-e533d4da3487.gif)

# Features
- Connecting directly to selected server's IP from SRB2/SRB2Classic/SRB2 Legacy/Ring Racers Master Server,
- Starting server and playing, or just creating dedicated one,
- Checking if server is reachable (using [jameds.org's Port Checker](https://www.jameds.org/SRB2/port)),
- Runs on Linux, macOS and Windows (Git Bash).

# Dependencies
- Basic system utilities like GNU Coreutils, BusyBox or macOS out-of-the-box system utilities,
- Bash or any POSIX compliant shell,
- Findutils,
- Which,
- Curl,
- Gawk,
- Ncurses.

Additionally, Windows users need to have installed Git Bash to run this script.

# Dependencies Installation
**Linux:** 
1. In terminal enter this following command:
- Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install make git debianutils coreutils findutils ncurses-bin curl gawk`,

- Arch/Arch based: `sudo pacman -S --needed make git which coreutils findutils ncurses curl gawk`,

- Gentoo/Gentoo based: `sudo emerge -av dev-vcs/git sys-apps/which sys-apps/coreutils sys-apps/findutils sys-libs/ncurses net-misc/curl sys-apps/gawk`,

- Fedora/Fedora based: `sudo dnf install make git which coreutils findutils ncurses curl gawk`,

- Fedora Silverblue/Fedora Kinoite/Universal Blue (Bazzite, Aurora): `rpm-ostree install -A --allow-inactive make git which coreutils findutils ncurses curl gawk`,

- RHEL/RHEL based: `sudo dnf install make git which coreutils findutils ncurses curl gawk`,

- openSUSE Leap/openSUSE Tumbleweed/openSUSE Leap based/openSUSE Tumbleweed based: `sudo zypper in make git which coreutils findutils ncurses curl gawk`,

- openSUSE MicroOS/openSUSE MicroOS based: `sudo transactional-update pkg in make git which coreutils findutils ncurses curl gawk`,

- Void/Void based: `sudo xbps-install make git which coreutils findutils ncurses curl gawk`,

- Alpine/Alpine based: `sudo apk add make git which coreutils findutils ncurses curl gawk`,

- Solus/Solus based: `sudo eopkg it make git which coreutils findutils ncurses curl gawk`,

- NixOS/NixOS based: `sudo nix profile install nixpkgs#gnumake nixpkgs#git nixpkgs#which nixpkgs#coreutils nixpkgs#findutils nixpkgs#ncurses nixpkgs#curl nixpkgs#gawk --extra-experimental-features 'nix-command flakes'` or set those packages in "environment.systemPackages = with pkgs;" in "/etc/nixos/configuration.nix", and then enter `sudo nixos-rebuild switch`.

- Immutable systems like Steam Deck's SteamOS need rootless method of getting dependencies to avoid issues with wiping out installed packages after system's update or not to be able to write to certain path, like "/usr/local":
	- Install dependencies with package manager [Homebrew](https://brew.sh/): `brew install make git coreutils findutils ncurses curl gawk`.

**Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 in [HERE](https://youtu.be/SWYqp7iY_Tc?t=439),

2. Git Bash can be found on start menu,

3. The rest of dependencies are installed, if you followed video.

**macOS:**
1. In terminal enter this following command:
- Homebrew: `brew install gawk curl`,
- MacPorts: `sudo port install gawk curl`.

# Installation
**Linux:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`,

3. Go to downloaded directory: `cd srb2srv`,

4. Enter `sudo make install`, which will install to "/usr/local/bin". You can specify your path with variable PREFIX, for example `make install PREFIX=$HOME/.local`, which will copy script to "$HOME/.local/bin". Alternatively manually place script to your path, which is readable by shell (PATH environment variable), and change script's permissions to be executable: `chmod 755 [path to srb2srv script]`,

5. Set environment variables from "Configuration" section of README.

**Windows:**
1. Open Git Bash,

2. Enter `git clone https://github.com/Bijman/srb2srv`,

3. Go to downloaded directory: `cd srb2srv`,

4. Enter `install -Dm755 srb2srv -t /usr/local/bin`,

5. Set environment variables from "Configuration" section of README.

**macOS:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2srv`,

3. Go to downloaded directory: `cd srb2srv`,

4. Enter `sudo make install`, which will install to "/usr/local/bin". You can specify your path with variable PREFIX, for example `make install PREFIX=$HOME/.local`, which will copy script to "$HOME/.local/bin". Alternatively manually place script to your path, which is readable by shell (PATH environment variable), and change script's permissions to be executable: `chmod 755 [path to srb2srv script]`,

5. Set environment variables from "Configuration" section of README.

# Configuration
**If you want to connect to server or start your own server in SRB2:**
1. Enter your path to SRB2 executable file ("lsdl2srb2", "lsdlsrb2", "srb2", "srb2win.exe", "srb2win64.exe", "srb2.exe", "Sonic Robo Blast 2") or just type "flatpak org.srb2.SRB2" (for installed Flatpaks, Linux only) in shell configuration file (for example ".bash_profile" or ".bashrc" or ".zshrc" in user's home directory): `export SRB2="[path to SRB2 executable file]"` or `export SRB2="flatpak org.srb2.SRB2"`,
- Note for macOS users: SRB2 executable file should be in "/Applications/Sonic Robo Blast 2.app/Contents/MacOS/Sonic Robo Blast 2", if "Sonic Robo Blast 2.app" or "Sonic Robo Blast 2 Kart.app" is installed in "/Applications",
2. Enter `source ~/.bash_profile` or `source ~/.bashrc` or `source ~/.zshrc` or restart terminal/Git Bash.

**If you want to connect to server or start your own server in SRB2Kart:**
1. Enter your path to SRB2Kart executable file ("lsdl2srb2kart", "srb2kart", "srb2kart.exe", "Sonic Robo Blast 2 Kart") or just type "flatpak org.srb2.SRB2Kart" (for installed Flatpaks, Linux only) in shell configuration file (for example ".bash_profile" or ".bashrc" or ".zshrc" in user's home directory): `export SRB2KART="[path to SRB2Kart executable file]"` or `export SRB2KART="flatpak org.srb2.SRB2Kart"`,
- Note for macOS users: SRB2Kart executable file should be in "/Applications/Sonic Robo Blast 2 Kart.app/Contents/MacOS/Sonic Robo Blast 2 Kart", if "Sonic Robo Blast 2 Kart.app" is installed in "/Applications".
2. Enter `source ~/.bash_profile` or `source ~/.bashrc` or `source ~/.zshrc` or restart terminal/Git Bash.

**If you want to connect to server or start your own server in Ring Racers:**
1. Enter your path to Ring Racers executable file ("ringracers", "ringracers.exe", "Ring Racers") or just type "flatpak org.kartkrew.RingRacers" (for installed Flatpaks, Linux only) in shell configuration file (for example ".bash_profile" or ".bashrc" or ".zshrc" in user's home directory): `export RINGRACERS="[path to Ring Racers executable file]"` or `export RINGRACERS="flatpak org.kartkrew.RingRacers"`,
- Note for macOS users: Ring Racers executable file should be in "/Applications/Ring Racers.app/Contents/MacOS/Ring Racers", if "Ring Racers.app" is installed in "/Applications".
2. Enter `source ~/.bash_profile` or `source ~/.bashrc` or `source ~/.zshrc` or restart terminal/Git Bash.

# Usage (from help text)
```
CLI for server related tools of SRB2/SRB2Classic/SRB2 Legacy/SRB2Kart/Ring Racers.

Usage: srb2srv [OPTION] <parameter>
  OPTIONS:
     -h, --help                                   Show this help text.
     -c, --checkport                              Check if SRB2 server is reachable.
     -d, --dedicated            <addon-path>      Start dedicated SRB2 server.
     -dc, --dedicatedclassic    <addon-path>      Start dedicated SRB2Classic (v2.2) server.
     -dk, --dedicatedkart       <addon-path>      Start dedicated SRB2Kart server.
     -dl, --dedicatedlegacy     <addon-path>      Start dedicated SRB2 Legacy (v2.1) server.
     -dr, --dedicatedringracers <addon-path>      Start dedicated Ring Racers server.
     -f, --filter               <filter-query>    Filter list of SRB2 servers by query like server name, IP, gametype or map.
     -fc, --filterclassic       <filter-query>    Filter list of SRB2Classic (v2.2) servers by query like server name, IP, gametype or room.
     -fk, --filterkart          <filter-query>    Filter list of SRB2Kart servers by query like server name, IP, gametype or kartspeed.
     -fl, --filterlegacy        <filter-query>    Filter list of SRB2 Legacy (v2.1) servers by query like server name, IP, gametype or room.
     -fr, --filterringracers    <filter-query>    Filter list of Ring Racers servers by query like server name, IP, gametype or kartspeed.
     -i, --ip                   <server-ip>       Join SRB2 server from IP.
     -ik, --ipkart              <server-ip>       Join SRB2Kart server from IP.
     -ir, --ipringracers        <server-ip>       Join Ring Racers server from IP.
     -k, --kart                                   Go to SRB2Kart Master Server.
     -l, --legacy                                 Go to SRB2 Legacy (v2.1) Master Server.
     -lc, --classic                               Go to SRB2Classic (v2.2) Master Server.
     -kr, --ringracers                            Go to Ring Racers Master Server.
     -p, --port                 <port-number>     Specify the local UDP port to use. Works with -c, -d, -dk, -dr, -s, -sk and -sr options.
     -r, --room                 <room-name>       Go to SRB2 Master Server room. Available parameters: "standard", "casual" and "custom".
     -s, --server               <addon-path>      Start SRB2 server and play.
     -sc, --serverclassic       <addon-path>      Start SRB2Classic (v2.2) server and play.
     -sk, --serverkart          <addon-path>      Start SRB2Kart server and play.
     -sl, --serverlegacy        <addon-path>      Start SRB2 Legacy (v2.1) server and play.
     -sr, --serverringracers    <addon-path>      Start Ring Racers server and play.

  EXAMPLES:
     1. Go to SRB2 Master Server and connect to selected server from list:
            srb2srv

     2. Go to Ring Racers Master Server and connect to selected server from list:
            srb2srv --ringracers

     3. Check if port for SRB2 server is opened (default port to be checked is 5029 without --port option):
            srb2srv --checkport --port 5030

     4. Run SRB2 server and add path to addon or directory of addons (default port to hosting server is 5029):
            srb2srv --server "$HOME/addon.pk3"

     5. Run SRB2Kart dedicated server with port 5030, and add path to addon or directory of addons (default port to hosting server is 5029 without --port option):
            srb2srv --dedicatedkart "$HOME/addon.pk3" --port 5030

     6. Join SRB2 server:
            srb2srv --ip 123.84.116.123:5029

     7. Go to SRB2 Master Server room. Available parameters: "standard", "casual" and "custom":
            srb2srv --room standard 

     8. Filter list of SRB2 servers by server name:
            srb2srv --filter "The Gaming Den - Vanilla"

     9. Filter list of SRB2Kart servers by kartspeed:
            srb2srv --filterkart "Normal"

  NOTES:
     - Exporting SRB2/SRB2Classic/SRB2 Legacy/SRB2Kart/Ring Racers executable file ("lsdl2srb2", "lsdlsrb2", "srb2", "srb2win.exe", "srb2win64.exe", "srb2.exe", "Sonic Robo Blast 2", "Sonic Robo Blast 2 Classic", "lsdl2srb2legacy", "srb2legacywin.exe", "srb2legacywin64.exe", "Sonic Robo Blast 2 Legacy", "lsdl2srb2kart", "srb2kart", "srb2kart.exe", "Sonic Robo Blast 2 Kart", "ringracers", "ringracers.exe", "Ring Racers") path or "flatpak [SRB2/SRB2Classic/SRB2 Legacy/SRB2Kart/Ring Racers Flatpak Application ID]" (for installed Flatpaks, Linux only) in "SRB2", "SRB2KART" or "RINGRACERS" environment variable to shell configuration file (for example in ".bashrc" or ".bash_profile") is required for script to work.
     Here are a few examples:
       SRB2
         1. Linux:
            - export SRB2="$HOME/Games/SRB2/lsdl2srb2",
            - export SRB2="$HOME/Games/SRB2/lsdlsrb2",
            - export SRB2="$HOME/Games/SRB2/srb2",
            - export SRB2="/usr/local/bin/srb2",
            - export SRB2="flatpak org.srb2.SRB2".

         2. Windows:
            - export SRB2="$HOME/Games/SRB2/srb2win.exe",
            - export SRB2="$HOME/Games/SRB2/srb2win64.exe",
            - export SRB2="$HOME/Games/SRB2/srb2.exe",
            - export SRB2="C:\Users\user\Games\SRB2\srb2win.exe".

         3. macOS:
            - export SRB2="/Applications/Sonic Robo Blast 2.app/Contents/MacOS/Sonic Robo Blast 2".

       SRB2Classic
         1. Linux:
            - export SRB2CLASSIC="$HOME/Games/SRB2CLASSIC/lsdl2srb2",
            - export SRB2CLASSIC="/usr/local/bin/srb2classic",
            - export SRB2CLASSIC="flatpak org.srb2.srb2-classic".

         2. Windows:
            - export SRB2CLASSIC="$HOME/Games/SRB2CLASSIC/srb2win.exe",
            - export SRB2CLASSIC="$HOME/Games/SRB2CLASSIC/srb2win64.exe",
            - export SRB2CLASSIC="C:\Users\user\Games\SRB2CLASSIC\srb2win64.exe".

         3. macOS:
            - export SRB2CLASSIC="/Applications/Sonic Robo Blast 2 Classic.app/Contents/MacOS/Sonic Robo Blast 2 Classic"."

       SRB2 Legacy
         1. Linux:
            - export SRB2LEGACY="$HOME/Games/SRB2LEGACY/lsdl2srb2legacy",
            - export SRB2LEGACY="/usr/local/bin/srb2legacy",
            - export SRB2LEGACY="flatpak org.srb2.srb2-legacy".

         2. Windows:
            - export SRB2LEGACY="$HOME/Games/SRB2LEGACY/srb2legacywin.exe",
            - export SRB2LEGACY="$HOME/Games/SRB2LEGACY/srb2legacywin64.exe",
            - export SRB2LEGACY="C:\Users\user\Games\SRB2LEGACY\srb2legacywin64.exe".

         3. macOS:
            - export SRB2LEGACY="/Applications/Sonic Robo Blast 2 Legacy.app/Contents/MacOS/Sonic Robo Blast 2 Legacy"."

       SRB2Kart
         1. Linux:
            - export SRB2KART="$HOME/Games/SRB2Kart/lsdl2srb2kart",
            - export SRB2KART="$HOME/Games/SRB2Kart/srb2kart",
            - export SRB2KART="/usr/local/bin/srb2kart",
            - export SRB2KART="flatpak org.srb2.SRB2Kart".

         2. Windows:
            - export SRB2KART="$HOME/Games/SRB2Kart/srb2kart.exe",
            - export SRB2KART="C:\Users\user\Games\SRB2Kart\srb2kart.exe".

         3. macOS:
            - export SRB2KART="/Applications/Sonic Robo Blast 2 Kart.app/Contents/MacOS/Sonic Robo Blast 2 Kart".

       RING RACERS
         1. Linux:
            - export RINGRACERS="$HOME/Games/RingRacers/ringracers",
            - export RINGRACERS="$HOME/Games/RingRacers/ringracers",
            - export RINGRACERS="/usr/local/bin/ringracers",
            - export RINGRACERS="flatpak org.kartkrew.RingRacers".

         2. Windows:
            - export RINGRACERS="$HOME/Games/RingRacers/ringracers.exe",
            - export RINGRACERS="C:\Users\user\Games\RingRacers\ringracers.exe".

         3. macOS:
            - export RINGRACERS="/Applications/Ring Racers.app/Contents/MacOS/Ring Racers".

     - This script does not set port forwarding and open port in system's firewall for you. You need to do this manually on your router and system. For more information read the guide in: https://www.jameds.org/portforward.

     - To automate inputting in script for hosting server, do for example 'echo "1\n3" | srb2srv -d [path to directory of addons for dedicated server]', which means it will make input to list dedicated server in Custom room on Master Server.

     - Full path to game's main configuration file can be set with SRB2MAINCFG, SRB2KARTMAINCFG or RINGRACERSMAINCFG variable to shell configuration file, otherwise script assumes default file, if SRB2MAINCFG, SRB2KARTMAINCFG or RINGRACERSMAINCFG is not set.

     - There is also additional SRB2CFG, SRB2KARTCFG and RINGRACERSCFG variables of other configuration files, which can temporary override settings of set SRB2MAINCFG, SRB2KARTMAINCFG and RINGRACERSCFG.

     - To turn off automatic restart of server after error, set environment variable "export NOSRB2SRVLOOP=1".

     - Other environment variables to use. To activate them with value "1", do for example "export SRB2SRVDEBUG=1":

         - SRB2SRVDEBUG - Getting verbose output from script. Useful for reporting issues in https://github.com/bijman/srb2srv/issues.
```

# Notes
     - Exporting SRB2/SRB2Classic/SRB2 Legacy/SRB2Kart/Ring Racers executable file ("lsdl2srb2", "lsdlsrb2", "srb2", "srb2win.exe", "srb2win64.exe", "srb2.exe", "Sonic Robo Blast 2", "Sonic Robo Blast 2 Classic", "lsdl2srb2legacy", "srb2legacywin.exe", "srb2legacywin64.exe", "Sonic Robo Blast 2 Legacy", "lsdl2srb2kart", "srb2kart", "srb2kart.exe", "Sonic Robo Blast 2 Kart", "ringracers", "ringracers.exe", "Ring Racers") path or "flatpak [SRB2/SRB2Classic/SRB2 Legacy/SRB2Kart/Ring Racers Flatpak Application ID]" (for installed Flatpaks, Linux only) in "SRB2", "SRB2KART" or "RINGRACERS" environment variable to shell configuration file (for example in ".bashrc" or ".bash_profile") is required for script to work.
     Here are a few examples:
       SRB2
         1. Linux:
            - export SRB2="$HOME/Games/SRB2/lsdl2srb2",
            - export SRB2="$HOME/Games/SRB2/lsdlsrb2",
            - export SRB2="$HOME/Games/SRB2/srb2",
            - export SRB2="/usr/bin/srb2",
            - export SRB2="flatpak org.srb2.SRB2".

         2. Windows:
            - export SRB2="$HOME/Games/SRB2/srb2win.exe",
            - export SRB2="$HOME/Games/SRB2/srb2win64.exe",
            - export SRB2="$HOME/Games/SRB2/srb2.exe",
            - export SRB2="C:\Users\user\Games\SRB2\srb2win.exe".

         3. macOS:
            - export SRB2="/Applications/Sonic Robo Blast 2.app/Contents/MacOS/Sonic Robo Blast 2".

      SRB2Classic
         1. Linux:
            - export SRB2CLASSIC="$HOME/Games/SRB2CLASSIC/lsdl2srb2",
            - export SRB2CLASSIC="/usr/local/bin/srb2classic",
            - export SRB2CLASSIC="flatpak org.srb2.srb2-classic".

         2. Windows:
            - export SRB2CLASSIC="$HOME/Games/SRB2CLASSIC/srb2win.exe",
            - export SRB2CLASSIC="$HOME/Games/SRB2CLASSIC/srb2win64.exe",
            - export SRB2CLASSIC="C:\Users\user\Games\SRB2CLASSIC\srb2win64.exe".

         3. macOS:
            - export SRB2CLASSIC="/Applications/Sonic Robo Blast 2 Classic.app/Contents/MacOS/Sonic Robo Blast 2 Classic"."

       SRB2 Legacy
         1. Linux:
            - export SRB2LEGACY="$HOME/Games/SRB2LEGACY/lsdl2srb2legacy",
            - export SRB2LEGACY="/usr/local/bin/srb2legacy",
            - export SRB2LEGACY="flatpak org.srb2.srb2-legacy".

         2. Windows:
            - export SRB2LEGACY="$HOME/Games/SRB2LEGACY/srb2legacywin.exe",
            - export SRB2LEGACY="$HOME/Games/SRB2LEGACY/srb2legacywin64.exe",
            - export SRB2LEGACY="C:\Users\user\Games\SRB2LEGACY\srb2legacywin64.exe".

         3. macOS:
            - export SRB2LEGACY="/Applications/Sonic Robo Blast 2 Legacy.app/Contents/MacOS/Sonic Robo Blast 2 Legacy"."

       SRB2Kart
         1. Linux:
            - export SRB2KART="$HOME/Games/SRB2Kart/lsdl2srb2kart",
            - export SRB2KART="$HOME/Games/SRB2Kart/srb2kart",
            - export SRB2KART="/usr/bin/srb2kart",
            - export SRB2KART="flatpak org.srb2.SRB2Kart".

         2. Windows:
            - export SRB2KART="$HOME/Games/SRB2Kart/srb2kart.exe",
            - export SRB2KART="C:\Users\user\Games\SRB2Kart\srb2kart.exe".

         3. macOS:
            - export SRB2KART="/Applications/Sonic Robo Blast 2 Kart.app/Contents/MacOS/Sonic Robo Blast 2 Kart".

       RING RACERS
         1. Linux:
            - export RINGRACERS="$HOME/Games/RingRacers/ringracers",
            - export RINGRACERS="$HOME/Games/RingRacers/ringracers",
            - export RINGRACERS="/usr/local/bin/ringracers",
            - export RINGRACERS="flatpak org.kartkrew.RingRacers".

         2. Windows:
            - export RINGRACERS="$HOME/Games/RingRacers/ringracers.exe",
            - export RINGRACERS="C:\Users\user\Games\RingRacers\ringracers.exe".

         3. macOS:
            - export RINGRACERS="/Applications/Ring Racers.app/Contents/MacOS/Ring Racers".

     - This script does not set port forwarding and open port in system's firewall for you. You need to do this manually on your router and system. For more information read the guide in: https://www.jameds.org/portforward.

     - To automate inputting in script for hosting server, do for example 'echo "1\n3" | srb2srv -d [path to directory of addons for dedicated server]', which means it will make input to list dedicated server in Custom room on Master Server.

     - Full path to game's main configuration file can be set with SRB2MAINCFG, SRB2KARTMAINCFG or RINGRACERSMAINCFG variable to shell configuration file, otherwise script assumes default file, if SRB2MAINCFG, SRB2KARTMAINCFG or RINGRACERSMAINCFG is not set.

     - There is also additional SRB2CFG, SRB2KARTCFG and RINGRACERSCFG variables of other configuration files, which can temporary override settings of set SRB2MAINCFG, SRB2KARTMAINCFG and RINGRACERSCFG.

     - To turn off automatic restart of server after error, set environment variable "export NOSRB2SRVLOOP=1".

     - Other environment variables to use. To activate them with value "1", do for example "export SRB2SRVDEBUG=1":

         - SRB2SRVDEBUG - Getting verbose output from script. Useful for reporting issues in https://github.com/bijman/srb2srv/issues.
