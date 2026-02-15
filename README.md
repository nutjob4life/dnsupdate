# Piedra Blanca DNS Updater

This contains configuration and documentation for using [dnsupdate](https://github.com/lopsided98/dnsupdate) with my [DynDNS Pro](https://account.dyn.com/) account to update host-level IP addresses mostly for helping with incoming connections from outside the premises of Piedra Blanca.


## 📀 Installation

Clone this repository

    git clone --quiet https://github.com/nutjob4life/dnsupdate
    cd dnsupdate

Make it a Python virtual environment and install the `dnsupdate` program:

    python3.13 -m venv .
    bin/pip install --quiet --upgrade pip
    bin/pip install --quiet --requirement requirements.txt

Create the `private.yaml` file with the following contents:
```yaml
---
service_ipv4: 'members.dyndns.org'
service_ipv6: 'members.dyndns.org'
username: 'USERNAME'
password: 'UPDATE-KEY'
hostname: 'HOSTNAME'
...
```
Substitute `USERNAME` and `UPDATE_KEY` with your credentials and `HOSTNAME` with the host entry you want updated.

Finally, run `crontab -e` to run it with a daily frequency:

    @daily /PATH/TO/dnsupdate/bin/dnsupdate /PATH/TO/dnsupdate/dnsupdate.conf


## 👩‍🎨 Creators

This configuration was made by [Sean Kelly](https://seankelly.biz/) for his home setup. Of course, plenty of [gratitude goes to dnsupdate](https://github.com/lopsided98/dnsupdate).


## 📃 License

The project is licensed under the [Apache version 2](LICENSE.md) license.
