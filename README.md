<p align="center">
  <a href="https://paybill.dev" target="_blank">
    <picture>
      <img src="./static/aws-security-group.png" alt="Logo" />
    </picture>
  </a>
</p>

# Terraform Module: Security Group  

## Overview

This Terraform module creates an AWS Security Group with fully customizable ingress and egress rules. It supports CIDR-based, IPv6, and security-group-based access rules using dynamic blocks, includes tagging, and outputs the security group ID.

<!-- BEGIN_TF_DOCS -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_security_group.sg](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_egress_rules"></a> [egress\_rules](#input\_egress\_rules) | Egress rules for the security groups. | <pre>map(object({<br/>    description       = optional(string)<br/>    from_port         = number<br/>    to_port           = number<br/>    protocol          = string<br/>    cidr_blocks       = optional(list(string))<br/>    security_group_id = optional(list(string))<br/>    ipv6_cidr_blocks  = optional(list(string))<br/>  }))</pre> | `{}` | no |
| <a name="input_ingress_rules"></a> [ingress\_rules](#input\_ingress\_rules) | Ingress rules for the security groups. | <pre>map(object({<br/>    description       = optional(string)<br/>    from_port         = number<br/>    to_port           = number<br/>    protocol          = string<br/>    cidr_blocks       = optional(list(string))<br/>    security_group_id = optional(list(string))<br/>    ipv6_cidr_blocks  = optional(list(string))<br/>    self              = optional(bool)<br/>  }))</pre> | `{}` | no |
| <a name="input_security_group_description"></a> [security\_group\_description](#input\_security\_group\_description) | Description of the security groups | `string` | `"my-security-group"` | no |
| <a name="input_security_group_name"></a> [security\_group\_name](#input\_security\_group\_name) | Prefix for the name of the security groups. | `string` | `"my-security-group"` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | Tags to assign the security groups. | `map(string)` | n/a | yes |
| <a name="input_vpc_id"></a> [vpc\_id](#input\_vpc\_id) | ID of the VPC to create the security groups in. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_id"></a> [id](#output\_id) | The ID of the security group |
<!-- END_TF_DOCS -->