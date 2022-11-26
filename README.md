# Damn Vulnerable DeFi Dockerfile
Docker container to setup Damn Vulnerable DeFi environment and expose SSH to connect with Visual Studio Code.

Original Git created by @tinchoabbate:
https://github.com/tinchoabbate/damn-vulnerable-defi

For further information on how to hack smart contracts with this CTF:
https://www.damnvulnerabledefi.xyz/

### Docker setup
To setup this docker container execute:

```
docker build -t dvdefi .
docker run --name dvdefi -d -p 22:22 dvdefi
```

### Default username & password
The default username and password for the SSH connection are ```gato:gato123```
To change creds during setup, change them on line 6 of Dockerfile:

```
RUN echo 'gato:gato123' | chpasswd
```

### Connect Visual Studio Code
- First of all, install any extension for SSH connections like "Remote - SSH" from Microsoft
<img src="https://github.com/Luchoane/Damn-Vulnerable-DeFi-Dockerfile/blob/main/imgs/ssh_plugin.PNG" title="Plugin" alt="Plugin"/>

- Connect to the docker server through Visual Studio Code with ```ssh username@local_ip_address```
- Load the Damn Vulnerable DeFi folder located at /home/username/damn-vulnerable-defi
<img src="https://github.com/Luchoane/Damn-Vulnerable-DeFi-Dockerfile/blob/main/imgs/load_folder.PNG" title="Load" alt="Load"/>

- Open a terminal and do a first run on the first challenge with ```npm run unstoppable```
- Code your exploit and testing again with ```npm run unstoppable```
<img src="https://github.com/Luchoane/Damn-Vulnerable-DeFi-Dockerfile/blob/main/imgs/success.PNG" title="Success" alt="Success"/>

## Disclaimer

All Solidity code, practices and patterns in this repository are DAMN VULNERABLE and for educational purposes only.
This exposes an SSH server in port 22.

DO NOT USE IN PRODUCTION.
