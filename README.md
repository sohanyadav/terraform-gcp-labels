# Terraform-Gcp-Labels
# Terraform Google Cloud Labels Module

## Table of Contents
- [Introduction](#introduction)
- [Usage](#usage)
- [Module Inputs](#module-inputs)
- [Module Outputs](#module-outputs)
- [Authors](#authors)
- [License](#license)

## Introduction
This Terraform module creates structured labels for GCP resources with specific attributes.

## Usage

- Use the module by referencing its source and providing the required variables.
## Example: Labels
```hcl
module "labels" {
  source = "https://github.com/sohanyadav/terraform-gcp-labels.git"
  name        = "labels"
  environment = "test"
  label_order = ["name", "environment"]
  attributes  = ["private"]
  extra_tags = {
  }
}
```
Please ensure you specify the correct 'source' path for the module.

## Module Inputs

- `name`: The name of the application or resource.
- `environment`: The environment in which the resource exists.
- `label_order`: The order in which labels should be applied.
- `business_unit`: The business unit associated with the application.
- `attributes`: Additional attributes to add to the labels.
- `extra_tags`: Extra tags to associate with the resource.

## Module Outputs
- This module currently does not provide any outputs.

# Examples
For detailed examples on how to use this module, please refer to the [example](https://github.com/sohanyadav/terraform-gcp-labels/tree/master/_example) directory within this repository.

## Authors
Your Name
Replace '[License Name]' and '[Your Name]' with the appropriate license and your information. Feel free to expand this README with additional details or usage instructions as needed for your specific use case.

## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/sohanyadav/terraform-gcp-labels/blob/master/LICENSE) file for details.



<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.14, < 2.0 |
| <a name="requirement_google"></a> [google](#requirement\_google) | >= 3.50, < 5.0 |

## Providers

No providers.

## Modules

No modules.

## Resources

No resources.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_enabled"></a> [enabled](#input\_enabled) | A boolean flag to enable/disable service-account . | `bool` | `true` | no |
| <a name="input_environment"></a> [environment](#input\_environment) | Environment (e.g. `prod`, `dev`, `staging`). | `string` | `""` | no |
| <a name="input_google_kms_crypto_key_enabled"></a> [google\_kms\_crypto\_key\_enabled](#input\_google\_kms\_crypto\_key\_enabled) | Set to false to prevent the module from creating any resources. | `bool` | `true` | no |
| <a name="input_google_kms_crypto_key_iam_member_enabled"></a> [google\_kms\_crypto\_key\_iam\_member\_enabled](#input\_google\_kms\_crypto\_key\_iam\_member\_enabled) | Set to false to prevent the module from creating any resources. | `bool` | `true` | no |
| <a name="input_google_kms_key_ring_enabled"></a> [google\_kms\_key\_ring\_enabled](#input\_google\_kms\_key\_ring\_enabled) | Set to false to prevent the module from creating any resources. | `bool` | `true` | no |
| <a name="input_key_algorithm"></a> [key\_algorithm](#input\_key\_algorithm) | The algorithm to use when creating a version based on this template. See the https://cloud.google.com/kms/docs/reference/rest/v1/CryptoKeyVersionAlgorithm for possible inputs. | `string` | `"GOOGLE_SYMMETRIC_ENCRYPTION"` | no |
| <a name="input_key_protection_level"></a> [key\_protection\_level](#input\_key\_protection\_level) | The protection level to use when creating a version based on this template. Default value: "SOFTWARE" Possible values: ["SOFTWARE", "HSM"] | `string` | `"SOFTWARE"` | no |
| <a name="input_key_rotation_period"></a> [key\_rotation\_period](#input\_key\_rotation\_period) | Generate a new key every time this period passes. | `string` | `"100000s"` | no |
| <a name="input_label_order"></a> [label\_order](#input\_label\_order) | Label order, e.g. sequence of application name and environment `name`,`environment`,'attribute' [`webserver`,`qa`,`devops`,`public`,] . | `list(any)` | <pre>[<br>  "name",<br>  "environment"<br>]</pre> | no |
| <a name="input_location"></a> [location](#input\_location) | Location for the keyring. | `string` | `"asia"` | no |
| <a name="input_managedby"></a> [managedby](#input\_managedby) | ManagedBy, opsstation | `string` | `"opsstation"` | no |
| <a name="input_name"></a> [name](#input\_name) | Name of the resource. Provided by the client when the resource is created. | `string` | `""` | no |
| <a name="input_purpose"></a> [purpose](#input\_purpose) | The immutable purpose of the CryptoKey. Possible values are ENCRYPT\_DECRYPT, ASYMMETRIC\_SIGN, and ASYMMETRIC\_DECRYPT. | `string` | `"ENCRYPT_DECRYPT"` | no |
| <a name="input_repository"></a> [repository](#input\_repository) | Terraform current module repo | `string` | `""` | no |
| <a name="input_role"></a> [role](#input\_role) | this role use for permissions | `string` | `""` | no |
| <a name="input_service_accounts"></a> [service\_accounts](#input\_service\_accounts) | List of comma-separated owners for each key declared in set\_owners\_for. | `list(string)` | `[]` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_id"></a> [id](#output\_id) | n/a |
| <a name="output_key"></a> [key](#output\_key) | n/a |
| <a name="output_keyring"></a> [keyring](#output\_keyring) | n/a |
| <a name="output_keyring_name"></a> [keyring\_name](#output\_keyring\_name) | n/a |
| <a name="output_keyring_resource"></a> [keyring\_resource](#output\_keyring\_resource) | n/a |
<!-- END_TF_DOCS -->