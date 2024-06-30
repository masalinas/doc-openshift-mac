## Description
Documentation deploy OpenShift 14.x in Mac M1

## Steps

- **STEO01**: Go this link: https://console.redhat.com/openshift/create/local and download your CLI for your architecture in our case the OpenShift Local file for **MacOS aarch64**. Install the crc CLI from apk downloaded in your computer

- **STEO02**: execute setup from crc CLI like this

```
$ crc setup

INFO Using bundle path /Users/miguel/.crc/cache/crc_vfkit_4.15.17_arm64.crcbundle
INFO Checking if running macOS version >= 13.x    
INFO Checking if running as non-root              
INFO Checking if crc-admin-helper executable is cached
INFO Checking if running on a supported CPU architecture
INFO Checking if crc executable symlink exists    
INFO Checking minimum RAM requirements            
INFO Check if Podman binary exists in: /Users/miguel/.crc/bin/oc
INFO Removing Podman binary from: /Users/miguel/.crc/bin/oc
INFO Checking if running emulated on Apple silicon
INFO Checking if vfkit is installed               
INFO Checking if CRC bundle is extracted in '$HOME/.crc'
INFO Checking if /Users/miguel/.crc/cache/crc_vfkit_4.15.17_arm64.crcbundle exists
INFO Getting bundle for the CRC executable        
INFO Downloading bundle: /Users/miguel/.crc/cache/crc_vfkit_4.15.17_arm64.crcbundle...
4.46 GiB / 4.46 GiB [-----------------------------------------------------------------------------------------------------------------------------------] 100.00% 3.25 MiB/s
INFO Uncompressing /Users/miguel/.crc/cache/crc_vfkit_4.15.17_arm64.crcbundle
crc.img:  31.00 GiB / 31.00 GiB [----------------------------------------------------------------------------------------------------------------------------------] 100.00%
oc:  117.28 MiB / 117.28 MiB [-------------------------------------------------------------------------------------------------------------------------------------] 100.00%
INFO Checking if old launchd config for tray and/or daemon exists
INFO Checking if crc daemon plist file is present and loaded
INFO Adding crc daemon plist file and loading it  
INFO Checking SSH port availability               
Your system is correctly setup for using CRC. Use 'crc start' to start the instance
```

- **STEO02**: execute start from crc CLI like this:

```
$ crc start

INFO Using bundle path /Users/miguel/.crc/cache/crc_vfkit_4.15.17_arm64.crcbundle
INFO Checking if running macOS version >= 13.x    
INFO Checking if running as non-root              
INFO Checking if crc-admin-helper executable is cached
INFO Checking if running on a supported CPU architecture
INFO Checking if crc executable symlink exists    
INFO Checking minimum RAM requirements            
INFO Check if Podman binary exists in: /Users/miguel/.crc/bin/oc
INFO Checking if running emulated on Apple silicon
INFO Checking if vfkit is installed               
INFO Checking if old launchd config for tray and/or daemon exists
INFO Checking if crc daemon plist file is present and loaded
INFO Checking SSH port availability               
INFO Loading bundle: crc_vfkit_4.15.17_arm64...   
INFO Creating CRC VM for OpenShift 4.15.17...     
INFO Generating new SSH key pair...               
INFO Generating new password for the kubeadmin user
INFO Starting CRC VM for openshift 4.15.17...     
INFO CRC instance is running with IP 127.0.0.1    
INFO CRC VM is running                            
INFO Updating authorized keys...                  
INFO Configuring shared directories               
INFO Check internal and public DNS query...       
INFO Check DNS query from host...                 
INFO Verifying validity of the kubelet certificates...
INFO Starting kubelet service                     
INFO Waiting for kube-apiserver availability... [takes around 2min]
INFO Adding user's pull secret to the cluster...  
INFO Updating SSH key to machine config resource...
INFO Waiting until the user's pull secret is written to the instance disk...
INFO Changing the password for the kubeadmin user
INFO Updating cluster ID...                       
INFO Updating root CA cert to admin-kubeconfig-client-ca configmap...
INFO Starting openshift instance... [waiting for the cluster to stabilize]
INFO Operator authentication is not yet available
INFO All operators are available. Ensuring stability...
INFO Operators are stable (2/3)...                
INFO Operators are stable (3/3)...                
INFO Adding crc-admin and crc-developer contexts to kubeconfig...
Started the OpenShift cluster.

The server is accessible via web console at:
  https://console-openshift-console.apps-crc.testing

Log in as administrator:
  Username: kubeadmin
  Password: nM7WX-G2QUy-NEfPd-nI6KP

Log in as user:
  Username: developer
  Password: developer

Use the 'oc' command line interface:
  $ eval $(crc oc-env)
  $ oc login -u developer https://api.crc.testing:6443
  ```

**NOTE**: if exist some error remove the last setup and start again

```
$ crc delete
```

## *STEP04*: Open Web console in your default browser
```
$ crc console
```
