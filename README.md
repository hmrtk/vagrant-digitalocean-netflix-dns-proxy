Setting Up a Netflix DNS Proxy using Docker on DigitalOcean by Vagrant
=================================

`vagrant-digitalocean-netflix-dns-proxy` contains a Vagrant file for running Docker on DigitalOcean and setting up a Netflix DNS Proxy using [Netflix-Proxy](https://github.com/ab77/netflix-proxy).

Features:

* Docker on Ubuntu
* Netflix DNS Proxy that uses BIND and sniproxy.


Prepare
-------

Sign up [DigitalOcean](https://www.digitalocean.com/?refcode=eca04fb036a5) and get your [digitalocean API key](https://cloud.digitalocean.com/settings/applications).

Install [Vagrant](https://www.vagrantup.com).

Install [Digital Ocean Vagrant Provider](https://github.com/smdahlen/vagrant-digitalocean).

```sh
vagrant plugin install vagrant-digitalocean
```

Check out the project.

```sh
git clone https://github.com/hmrtk/vagrant-digitalocean-netflix-dns-proxy.git && cd vagrant-digitalocean-netflix-dns-proxy
```

Open Vagrantfile in an editor of your choice, use the [digitalocean API key](https://cloud.digitalocean.com/settings/applications) and set it as the token value in Vagrantfile:

```sh
provider.token = 'DIGITAL_OCEAN_API_KEY_GOES_HERE'
```

Note
----
This Vagrant file would use the smallest droplet of digitalocean in NYC3 zone. You can change the zone and the size of instance in the Vagrant file:

```sh
provider.region = 'nyc3'
provider.size = '512mb'
```
Run
---

Create a new droplet as follows:

```sh
vagrant up
```

Destroy the droplet as follows:

```sh
vagrant destroy
```
