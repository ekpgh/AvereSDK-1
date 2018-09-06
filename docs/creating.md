# Creating and managing vFXT clusters - About the vfxt.py script

The vfxt.py script is a command-line tool for creating and managing Avere clusters in cloud-based virtual computing environments. The script can create new Avere clusters - including creating the vFXT nodes that make up the cluster and establishing cloud storage as core filers; destroy existing clusters (including the vFXT nodes); create and add new nodes to a cluster; and do basic cluster configuration tasks. 

For ongoing cluster administration, use the Avere Control Panel. Read the Avere Cluster [Configuration Guide](<http://library.averesystems.com/#operations>) for more details. 

The vfxt.py script can be used with any of the cloud computing providers that Avere OS supports. Environment setup requirements are different for the different platforms, and the exact commands available vary by cloud computing provider.

This document gives a basic overview of the vfxt.py script and its options. It includes information about commands specific to Microsoft Azure, Amazon Web Services, and Google Compute Project cloud services. However, setting up a cloud project and configuring it to provide an Avere vFXT cluster includes many more steps than are documented here. Project creation, identity and access management, networking, quota and billing concerns, security, and many other topics are explained in detail in the Avere vFXT Installation Guide customized for your cloud provider. Read the complete details here: 

* [vFXT Installation Guide for Amazon Web Services](<http://library.averesystems.com/#vfxt>) 
* [vFXT Installation Guide for Google Cloud Platform](<http://library.averesystems.com/#vfxt>)
* vFXT Installation Guide for Microsoft Azure – coming soon; read current online documentation [here](<http://aka.ms/averedocs>). 

The command `vfxt.py --help` gives a full list of command options, including provider-specific functionality. 

## Installing and Setting Up the vfxt.py Script

You can run vfxt.py from any UNIX-style console environment that has access to your cloud computing resources. The simplest option is to create a Linux instance within the cloud environment, and install vfxt.py in that virtual machine. Alternatively, you can use a console from a remote Linux or Mac OS environment, as long as it has IP connectivity to your cloud instances. 

> Tip: For Microsoft Azure, a preconfigured Cluster Controller Node virtual machine image is available in the Azure Marketplace. Search for “Avere” to find the image. This image is preconfigured with required software to create and manage Microsoft Avere vFXT clusters.  

### Cloud Console Setup

If setting up a Linux instance in the cloud, follow these guidelines. 

* Create a VM instance of any size.
* The instance must have the privileges to create other instances. Read the requirements for your cloud provider to learn how to configure the VM that provides your vfxt.py console. 
* Install a recent Linux distribution from GNU, Debian, Red Hat, or CentOS. Follow the instructions in [vfxt.py Software Requirements](#vfxt.py-software-requirements), below, for installing additional required packages. 

### Remote Console Setup 

If using a console from a system outside the cloud environment, make sure it can access the instances within your cloud environment. Read your cloud provider’s documentation to learn how to use a VPN or other utility to provide IP connectivity to your cloud instances. 

Install the software described in [vfxt.py Software Requirements](#vfxt.py-software-requirements), below. 

## vfxt.py Software Requirements

Before using vfxt.py, make sure that your Linux environment includes all of the necessary software packages. 

### 1. Check security prerequisites and Python version

The vfxt.py script requires Python version 2.7.9 or later. Also, check that the system used for creating and managing the vFXT cluster meets the software requirements for securely administering an Avere cluster, as described in the appendix of the Avere OS Configuration Guide.

### 2. Update system dependencies 

In this step, make sure that the software needed to run vfxt.py is installed and configured in the shell system. Python, SSL, and a foreign function interface (FFI) package are required. The steps are different depending on the Linux distribution:

* If using Ubuntu or another Debian-based Linux distribution:

  ```bash
  sudo apt-get update 
  sudo apt-get install python-pip
  ```

* If using Red Hat Enterprise Linux or CentOS: 

  ```bash
  sudo wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
  sudo rpm -ivh epel-release-latest-7.noarch.rpm
  sudo yum install -y python-pip
  ```

### 3. Update Python dependencies

Ensure that the Python installation has the latest versions of the API library for your cloud provider: 

* Boto AWS API library if using AWS 
* Azure Python SDK if using Azure
* Google API client library if using GCE

This command can be used with any of the three cloud providers to install the needed library. 
`pip install --user --upgrade boto requests google-api-python-client azure`

> Note: The `azure` package is a meta-package that downloads a full set of Azure libraries. If you will not be working with Microsoft Azure, you can omit that term from the command. To install only the Azure packages, use `$ pip install –-user azure`


## Downloading and Installing vfxt.py

The vfxt.py script is published in the Python Package Index (PyPI) and also available from the Avere SDK GitHub page. 

The easiest way to install vfxt.py is by using pip to automatically download and install the script and dependencies:
`pip install --user vFXT`

The `--user` option installs vfxt.py in `site.USER_BASE`, which defaults to `~/.local` on most UNIX-style systems. Read the [Python site.py documentation](<https://docs.python.org/2/library/site.html#site.USER_BASE>) to learn more.  

Release archives also are available from <https://github.com/AvereSystems/vFXT.py/releases>. (This is the same release available with pip but in a standalone archive format.)

You can test that the script is active by issuing the help command.
`vfxt.py --help`

If you see the help text, the test was successful. If you do not see the vfxt.py help text, check the software requirements and try the installation again. 

## Configuring the Cloud Environment 

Before you can use vfxt.py to create or modify Avere clusters, you must have a cloud account set up with a supported provider, and appropriate environment configuration. 

Regardless of whether you use vfxt.py on a virtual machine inside your cloud environment, or from a console outside the cloud, the following basic requirements apply: 

* vfxt.py must be able to make contact with the cloud provider's API endpoints (a proxy service might be required). 
* vfxt.py must be able to authenticate to the cloud environment. 
* vfxt.py must have permission to create and destroy virtual machine instances in the cloud environment. 

The details vary greatly by cloud provider. Read the detailed Avere vFXT Installation Guide for your cloud compute provider for complete information about setting up projects, network configuration, security and privileges, and other vital information before attempting to use vfxt.py. 

* vFXT Installation Guide for Amazon Web Services 
* vFXT Installation Guide for Google Cloud Platform
* vFXT Installation Guide for Microsoft Azure (coming soon)

These appendixes also give provider-specific information about using vfxt.py on particular cloud systems. 
* Quick Reference - Using vfxt.py with Amazon Web Services 
* Quick Reference - Using vfxt.py with Google Cloud Platform 
* Quick Reference – Using vfxt.py with Microsoft Azure 

 