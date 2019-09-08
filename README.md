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

# Set up Docker

- Firstly you need to download and install docker from https://hub.docker.com/
- To make your docker.exe runnable from WSL without having to write docker.exe you can instead use an alias, simply open your Bash.exe and run `echo "alias docker=docker.exe" >> ~/.bash_aliases` this will append the string `alias docker=docker.exe` your .bash_aliases file located in your home directory ( ~/ )

# Set up MongoDB

### With Docker

- You can run mongo db as a docker container and exposing the port used by mongo in the docker container to the host system to make it accessible as if it was running normally on your system.
- `docker run --name local-mongo -d -p 27017:27017 -v ~/data/mongo:/data/db mongo:latest`
- The above command will run a docker container with the name `local-mongo` in daemon mode with the port-mappings `27017` from the docker container to `27017` on the host system, i.e your windows machine. Lastly it will map the data folder from the docker container to your system so that the data is not cleared on each run.
- To start the local mongo server you can then run `docker start local-mongo`

### Regular install

- TODO

# Set up Redis

### With Docker

- You can run redis db as a docker container and exposing the port used by redis in the docker container to the host system to make it accessible as if it was running normally on your system.
- `docker run --name local-redis -d -p 6379:6379 -v ~/data/redis:/data redis:latest redis-server`
- The above command will run a docker container with the name `local-mongo` in daemon mode with the port-mappings `6379` from the docker container to `6379` on the host system, i.e your windows machine. Lastly it will map the data folder from the docker container to your system so that the data is not cleared on each run.
- To start the local redis server you can then run `docker start local-redis`

## Regular install

- TODO

# Set up Java and Maven

#### This sets up Java and Maven the regular windows way

- Download OpenJDK 12 from https://jdk.java.net/12/ (select the windows alternative)
- Extract the folder to any place you like, but keep it on the windows filesystem or else some applications will have trouble finding the java.exe
- Download Maven from https://maven.apache.org/download.cgi (select the binary version)
- Extract to anywhere you like but as with Java, keep the files on the windows filesystem.

- Next you need to add some environment variables \
  ![some text]("assets/envs1.png") \
  ![some text2]("assets/envs2.png") \
  ![some text3]("assets/envs3.png") \
  ![some text4]("asset/envs4.png")

- To see that it worked you should now the able to run (in your windows command line) `java --version` or if you do it in WSL `java.exe --version`
- For maven you run `mvn -v`
