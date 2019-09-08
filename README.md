# Getting started @ Qopla (Windows and WSL)

### Enabling WSL on your machine

- Run Windows Powershell as administrator.
- Paste the following into the terminal and follow the instructions. `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`
- Restart computer when prompted.

### Running a Linux-distro on your machine

- Go to Microsoft store and search for Ubuntu (in this case) and install it.
- When installation is complete run Bash.exe and follow the instructions.
- You should now have a UNIX-environment running in Windows.

# Set up Git

- By default Ubuntu comes with an older version of Git, to fix this you need to add a package repository to your Ubuntu package manager.
- Open Bash.exe and paste the following into the terminal. `sudo add-apt-repository ppa:git-core/ppa`
- Once that is done you can now run `sudo apt update && sudo apt install git`

# Set up Node and NPM

#### The following instructions installs node and npm on your WSL-environment only

- Go to https://github.com/nvm-sh/nvm and follow the instructions for how to install nvm
- When nvm has been installed you can run Bash.exe and paste the following into the terminal `nvm install lts/*` to install the latest LTS-release of node. This will also set your default node version to lts/\*
- To see your installed versions of node run the following command `nvm list`
- And to use a specific version of node you type `nvm use <your version>`

# Set up YarnPKG

- Open Bash.exe and run the following command `curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -`
- Then run `echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list`
- And finally if you are using nvm `sudo apt update && sudo apt install --no-install-recommends yarn` else just run `sudo apt update && sudo apt install yarn`

# Set up VSCode

- Download VSCode from https://code.visualstudio.com/ and install it.
- Plugins
  - Debugger for Chrome
  - Docker
  - Remote - WSL
  - Babel Javascript
  - ESLint
  - GitLens
  - Prettier
