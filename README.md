Terraform Module for creating Smart Access Gateway on Alibaba Cloud.

terraform-alicloud-sag
=====================================================================

English | [简体中文](https://github.com/terraform-alicloud-modules/terraform-alicloud-sag/blob/main/README-CN.md)

This module is used to create Smart Access Gateway on Alibaba Cloud.

These types of resources are supported:

* [alicloud_sag_acl](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/sag_acl)
* [alicloud_sag_acl_rule](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/sag_acl_rule)

## Usage

```hcl
module "example" {
  source     = "terraform-alicloud-modules/sag/alicloud"
  #alicloud_sag_acl
  create_acl = true
  acl_name   = "tf-test-sag"

  #alicloud_sag_acl_rule
  create_acl_rule   = true
  rule_description  = "tf-test-sag"
  policy            = "accept"
  ip_protocol       = "ALL"
  direction         = "in"
  source_cidr       = "10.10.1.0/24"
  source_port_range = "-1/-1"
  dest_cidr         = "192.168.1.0/24"
  dest_port_range   = "-1/-1"
  priority          = 1
}
```
## Examples

* [complete example](https://github.com/terraform-alicloud-modules/terraform-alicloud-sag/tree/main/examples/complete)

## Notes

* This module using AccessKey and SecretKey are from `profile` and `shared_credentials_file`. If you have not set them
  yet, please install [aliyun-cli](https://github.com/aliyun/aliyun-cli#installation) and configure it.

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | > = 0.13 |
| <a name="requirement_alicloud"></a> [alicloud](#requirement\_alicloud) | > = 1.60.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_alicloud"></a> [alicloud](#provider\_alicloud) | > = 1.60.0 |

## Submit Issues

If you have any problems when using this module, please opening
a [provider issue](https://github.com/aliyun/terraform-provider-alicloud/issues/new) and let us know.

**Note:** There does not recommend opening an issue on this repo.

## Authors

Created and maintained by Alibaba Cloud Terraform Team(terraform@alibabacloud.com).

## License

MIT Licensed. See LICENSE for full details.

## Reference

* [Terraform-Provider-Alicloud Github](https://github.com/aliyun/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs)
