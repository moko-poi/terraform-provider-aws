---
subcategory: "EC2 (Elastic Compute Cloud)"
layout: "aws"
page_title: "AWS: aws_ec2_instance_type_offering"
description: |-
  Information about single EC2 Instance Type Offering.
---


<!-- Please do not edit this file, it is generated. -->
# Data Source: aws_ec2_instance_type_offering

Information about single EC2 Instance Type Offering.

## Example Usage

```typescript
// Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { DataAwsEc2InstanceTypeOffering } from "./.gen/providers/aws/data-aws-ec2-instance-type-offering";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new DataAwsEc2InstanceTypeOffering(this, "example", {
      filter: [
        {
          name: "instance-type",
          values: ["t2.micro", "t3.micro"],
        },
      ],
      preferredInstanceTypes: ["t3.micro", "t2.micro"],
    });
  }
}

```

## Argument Reference

The following arguments are supported:

* `filter` - (Optional) One or more configuration blocks containing name-values filters. See the [EC2 API Reference](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeInstanceTypeOfferings.html) for supported filters. Detailed below.
* `locationType` - (Optional) Location type. Defaults to `region`. Valid values: `availabilityZone`, `availabilityZoneId`, and `region`.
* `preferredInstanceTypes` - (Optional) Ordered list of preferred EC2 Instance Types. The first match in this list will be returned. If no preferred matches are found and the original search returned more than one result, an error is returned.

### filter Argument Reference

* `name` - (Required) Name of the filter. The `location` filter depends on the top-level `locationType` argument and if not specified, defaults to the current region.
* `values` - (Required) List of one or more values for the filter.

## Attribute Reference

In addition to all arguments above, the following attributes are exported:

* `id` - EC2 Instance Type.
* `instanceType` - EC2 Instance Type.

## Timeouts

[Configuration options](https://developer.hashicorp.com/terraform/language/resources/syntax#operation-timeouts):

- `read` - (Default `20M`)

<!-- cache-key: cdktf-0.17.1 input-b9a0baa6d38287dcfdc6f70833e23287a617a652af798b75206cc22860a785e7 -->