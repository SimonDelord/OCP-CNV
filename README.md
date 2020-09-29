# OCP-CNV
Files for OCP CNV

These are several files used in the deployment of VMs in OpenShift Virtualisation.
The first one is a vanilla flavoured VM that can be spun up and logged into using fedora/fedora

The second one (FedoraVM-multiNIC.yaml) , makes use of Multus to have more than one vNIC attached to it. 
Multus networking must be configured by modifying the networks.operator.openshift.io cluster (oc edit networks.operator.openshift.io cluster).

The third one (FedoraVM-multiNIC-noDefaultNIC.yaml), makes use of Multus again and has 2 vNICs attached to it (but not the default one).
Interestingly, for this one, when looking at the PoD, it is defined with 3 interfaces (the default and the 2 multus ones) while when logging into the VM (fedora/fedora) only 2 interfaces (the multus ones) appear.
