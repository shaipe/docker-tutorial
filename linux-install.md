# Install Docker & Docker Compose - Centos 7

## Step 1 — Install Docker

### Install needed packages:

```bash
$ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

Configure the docker-ce repo:
```bash
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
Install docker-ce:
```bash
$ sudo yum install docker-ce
```
Add your user to the docker group with the following command.
```bash
$ sudo usermod -aG docker $(whoami)
```
Set Docker to start automatically at boot time:
```bash
$ sudo systemctl enable docker.service
```
Finally, start the Docker service:
```bash
$ sudo systemctl start docker.service
```
Step 2 — Install Docker Compose

Install Extra Packages for Enterprise Linux

```bash
$ sudo yum install epel-release
```
Install python-pip

```bash
$ sudo yum install -y python-pip
```
Then install Docker Compose:

```bash
$ sudo pip install docker-compose
```

You will also need to upgrade your Python packages on CentOS 7 to get docker-compose to run successfully:

```bash
$ sudo yum upgrade python*
```
To verify a successful Docker Compose installation, run:

```bash
$ docker-compose version
```