# vkmg
VK music getter.

Allows to download music from VK controlling headless Firefox with
[Selenium](http://docs.seleniumhq.org)
intercepting AJAX requests for tracks using
[Browsermob-Proxy](https://github.com/lightbody/browsermob-proxy).

## Prerequisites
- Linux box
- Java
- Python 3

## Installation

##### Get project
```bash
git clone https://github.com/Suenweek/vkmg.git
```

##### Create virtual environment
```bash
virtualenv -p python3 venv
```

##### Install requirements
```bash
venv/bin/pip install -r requirements.txt
```

##### Get Geckodriver
Download binaries or build from source from
[here](https://github.com/mozilla/geckodriver/releases).

##### Get Browsermob-Proxy
Download binaries or build from source from
[here](https://github.com/lightbody/browsermob-proxy/releases).

##### Install certificate for handling HTTPS
1. Create new
[firefox profile](https://support.mozilla.org/en-US/kb/profile-manager-create-and-remove-firefox-profiles).

2. Start Firefox using created profile.

3. Download certificate from [here](https://github.com/lightbody/browsermob-proxy/blob/master/browsermob-core/src/main/resources/sslSupport/ca-certificate-rsa.cer)
or make your own.

4. Install the certificate into the profile.

## Configuration
##### Set env vars
1. Create a copy of `env_template.sh` named `env.sh`
```bash
cp env_template.sh env.sh
```

2. Set adequate vars in `env.sh` using your favorite text editor.

3. Export them to current terminal session:
```bash
source env.sh
```

## Usage
```bash
./vkmg.py
```

##### Parameters
`-h / --help`

Show help message and exit.

`-t TARGET_VK_USER_ID / --target TARGET_VK_USER_ID`

ID of vk user whose tracks to get. Int. Required parameter.

`-o TRACKS_DIR / --output TRACKS_DIR`

Directory to save tracks to. Defaults to `tracks`.
If the directory does not exist, it will be created.

`-n NUMBER / --number NUMBER`

Number of tracks to get. Int. Defaults to `3`.
