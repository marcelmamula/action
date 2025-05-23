# Ansible Playbook - SAP Business Suite with SAP ASE Sandbox installation

This Ansible Playbook can be executed with:
- Ansible to provision hosts
- Ansible + Terraform to provision hosts
- Existing hosts

This Ansible Playbook can be targeted at the following Infrastructure Platforms:
- Amazon Web Services (AWS)
- Google Cloud Platform (GCP)
- IBM Cloud
- Microsoft Azure (MS Azure)
- OVirt
- VMware

SAP Business Suite with SAP ASE Sandbox installation:
- Sandbox System definition by SAP: all SAP ASE and SAP NetWeaver instances run on a single host.
- System Topology/Architecture: a Sandbox System is commonly referred as Two-Tier Architecture, may also be known as OneHost or Central System.
- Note: This Ansible Playbook is not available for IBM Power Little Endian (ppc64le); all prior SAP Software without SAP HANA was for IBM Power Big Endian (ppc64) only.

SAP Business Suite, aka. SAP ECC, software versions:
EhP8

---

## Execution of Ansible Playbook

Prior to execution, please read the [full documentation of the Ansible Playbooks for SAP](../../docs/README.md) for the capabilities and different execution methods.

## Execution outcome

When executing this Ansible Playbook for SAP, the following hosts are provisioned (unless an Ansible Inventory is provided for existing hosts):
1. Host for SAP ASE Database Server and SAP NetWeaver Application Server (ABAP) - Central Services (ASCS) and Primary Application Server (PAS)

The sequence of a Standard System installation is:
- `SWPM`: Install SAP ASE database server
- `SWPM`: Install SAP NetWeaver Application Server (ABAP) and Installation Export to Database (i.e. Database Load)

This therefore matches to the SAP SWPM Product ID prefixes that are executed in sequence:
- `NW_ABAP_OneHost`, Central Services, Primary Application Server
