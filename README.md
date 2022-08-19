# Packer Example - Red Hat Enterprise Linux 8 Vagrant Box using Ansible provisioner

This example build configuration installs and configures RHEL 8 x86_64 with a non-interactive kickstart file, and then generates a Vagrant box files, for:

- VirtualBox

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

- [Packer](http://www.packer.io/)
- [Vagrant](http://vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/) (if you want to build the VirtualBox box)

You must have a Red Hat Subscription to download the Red Hat Enterprise Linux 8 iso. If you don't, [create an account](https://developers.redhat.com) and accept the terms and conditions of the Red Hat Developer Program, which provides no-cost subscriptions for development use only.

## Usage

- Make sure all the required software (listed above) is installed.
- cd to the directory containing this README.md file,
- Create `iso/` directory and move inside your Red Hat Enterprise Linux iso.
- Edit rhel8.json file, check if `iso_urls` and `iso_checksum` match your RHEL iso.
- add your kickstart file into the `http/` dir and name it `ks.cfg`. 
> Part of the config for packer and vagrant is pretty standard to create a vagrant user with vagrant as password. This packer and vagrant config reflect that standard practice. You must change both rhel8.json and Vagrantfile if you utilize a different user and pass.


- Finally run:
 
```
    $ packer build rhel8.json
```

After a few minutes, Packer should tell you the box was generated successfully.

## Testing built boxes

There's an included Vagrantfile that allows quick testing of the built Vagrant boxes. From this same directory, run one of the following commands after building the boxes:

```
    # For VirtualBox:
    $ vagrant up virtualbox --provider=virtualbox
```

## TODO

- Add registration to Satellite.
