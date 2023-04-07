<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | 4.60.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 4.60.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_cloudwatch_event_rule.lambda_trigger](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/resources/cloudwatch_event_rule) | resource |
| [aws_cloudwatch_event_target.event_target](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/resources/cloudwatch_event_target) | resource |
| [aws_iam_role.iam_for_lambda](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/resources/iam_role) | resource |
| [aws_lambda_function.cost_alert](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/resources/lambda_function) | resource |
| [aws_lambda_permission.allow_events_bridge_to_run_lambda](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/resources/lambda_permission) | resource |
| [aws_iam_policy_document.assume_role](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_policy_document.inline_policy](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/data-sources/iam_policy_document) | data source |
| [aws_kms_secrets.secret_value](https://registry.terraform.io/providers/hashicorp/aws/4.60.0/docs/data-sources/kms_secrets) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_alert_threshold"></a> [alert\_threshold](#input\_alert\_threshold) | integer representing the % above which alerts will be sent to slack | `number` | n/a | yes |
| <a name="input_alerts_only"></a> [alerts\_only](#input\_alerts\_only) | the lambda will only post messages if a threshold is exceeded (alerts only mode). If set to false (a.k.a. scheduled mode) messages will be sent regularly | `bool` | `true` | no |
| <a name="input_encripted_slack_webhook_url"></a> [encripted\_slack\_webhook\_url](#input\_encripted\_slack\_webhook\_url) | encript the webhook URL with KMS, and use it in this variable. See readme.md | `string` | n/a | yes |
| <a name="input_frequency"></a> [frequency](#input\_frequency) | number of days to run the lambda (cron formating is also accepted) | `string` | `"rate(1 day)"` | no |
| <a name="input_image_uri"></a> [image\_uri](#input\_image\_uri) | URI of the repo where the lambda image is stored | `string` | n/a | yes |
| <a name="input_name"></a> [name](#input\_name) | name prefix to be applied to all resources | `string` | `"cost_alert"` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_lambda_arn"></a> [lambda\_arn](#output\_lambda\_arn) | n/a |
<!-- END_TF_DOCS -->