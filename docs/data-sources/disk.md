---
page_title: "rustack_disk Data Source - terraform-provider-rustack"
---
# rustack_disk (Data Source)

Get information about a Disk for use in other resources. 

## Example Usage

```hcl

data "rustack_project" "single_project" {
    name = "Terraform Project"
}

data "rustack_vdc" "single_vdc" {
    project_id = "${data.rustack_project.single_project.id}"
    name = "Terraform VDC"
}

data "rustack_disk" "single_disk" {
    vdc_id = data.rustack_vdc.single_vdc.id
    name = "Disk 2"
}

```
## Schema

### Required

- **name** (String) name of the disk
- **vdc_id** (String) id of the VDC

### Read-Only

- **id** (String) id of the Disk
- **size** (Number) the size of the Disk in gigabytes
- **storage_profile_id** (String) the id of the StorageProfile
- **storage_profile_name** (String) the name of the StorageProfile


