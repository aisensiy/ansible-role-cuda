Ansible Role Cuda
=========

Install Nvidia cuda toolkit for deeplearning frameworks.

Requirements
------------

The machine should have at least one cuda compatible gpu and compatible kernel version. For more information please go to [cuda installation guide](http://docs.nvidia.com/cuda/cuda-installation-guide-linux/#axzz4VZnqTJ2A).

This ansible role is only tested on ansible 2.5+.

Role Variables
--------------

```yaml
cuda_deb_file: "<deb file download from nvidia with network installation option>"
cuda: "<the cuda version of your deb file>"
cudnn_deb_file: "<the whole cudnn deb file host by your self>"
```

First, pick right cuda toolkit for you from [CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive). Choose the deb network version, download it in your `files` folder and put the name to `cuda_deb_file`, right now this ansible script can only support deb(network) installation workflow.

Then download the cudnn deb file compatible with the cudn toolkit, the nvidia require login to download the cudnn lib so your have to download it and host it in somewhere else (like s3) for auto download to your server. Then put the url in `cudnn_deb_file`.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: cuda
  roles:
    - role: ansible-role-cuda
```

License
-------

MIT