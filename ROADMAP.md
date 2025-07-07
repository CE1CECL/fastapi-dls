# Roadmap

I am planning to implement the following features in the future.

## Patching Endpoint

A (optional) Path-Variable to `gridd-unlock-patcher` which enables an additional endpoint.
Here you can upload your `nvidia-gridd` binary or `nvxdapix.dll` which then will be patched and responded.

## All-In-One Installer Script Endpoint

A new all-in-one installer endpoint
(here a script is returned for linux or windows which then could be called like
curl https://<fastapi-dls>/-/install/deb | sh which then
download and place a client-token in the right directory, patch your girdd / dll and restart nvidia-gridd service)

## HA - High Availability

Support Failover-Mode (secondary ip address) as in official DLS.

**Note**: There is no Load-Balancing / Round-Robin HA Mode supported! If you want to use that, consider to use 
Docker-Swarm with shared/cluster database (e.g. postgres).

*See [ha branch](https://git.collinwebdesigns.de/oscar.krause/fastapi-dls/-/tree/ha) for current status.*


## UI - User Interface

Add a user interface to manage origins and leases.

*See [ui branch](https://git.collinwebdesigns.de/oscar.krause/fastapi-dls/-/tree/ui) for current status.*


## Config Database

Instead of using environment variables, configuration files and manually create certificates, store configs and
certificates in database (like origins and leases). Also, there should be provided a startup assistant to prefill 
required attributes and create instance-certificates. This is more user-friendly and should improve fist setup.
