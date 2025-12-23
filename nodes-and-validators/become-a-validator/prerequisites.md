# Prerequisites

**Hardware and Software Requirements (Recommended)**

(https://docs.jibchain.net/nodes-and-validators/become-a-validator/prerequisites#hardware-and-software-requirements-recommended)

* CPU >= 2 `core`
* RAM >= 4 `GiB`
* Disk Space >= 50`GiB (SSD)`
* Linux OS `(Ubuntu or Debian)`
* Docker
* Build essential tools:

{% code title="Install build-essential" %}
```bash
sudo apt update && sudo apt install build-essential
```
{% endcode %}

* Editor software on the Linux command line:
  * `vim` or `nano`
* Install for `Debian`: https://docs.docker.com/engine/install/debian/
* Install for `Ubuntu`: https://docs.docker.com/engine/install/ubuntu/

Or install Docker one Command

```bash
curl https://get.docker.com | sh
```

***

**Software Checklist**

{% stepper %}
{% step %}
### Docker

Check Docker is installed:

{% code title="Check docker version" %}
```bash
docker -v
```
{% endcode %}

Example output:

```
Docker version 23.0.5, build bc4487a
```
{% endstep %}

{% step %}
### Docker Compose

Check Docker Compose is installed:

{% code title="Check docker compose version" %}
```bash
docker compose version
```
{% endcode %}

Example output:

```
Docker Compose version v2.17.3
```
{% endstep %}
{% endstepper %}
