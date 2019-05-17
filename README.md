# terraform-s3-cloudfront-site

A Terraform module to create an AWS Cloudfront Distrobution backed by an S3 Bucket

## Usage

```hcl
module "site" {
  source    = "github.com/azaveakyeotic/terraform-s3-cloudfront-site?ref=1.0.0"
  site_name = "your-website.com"
  cert_arn  = "${var.your-cert-arn}"
}
```

## Variables

- `site_name` - The domain for your site, (e.g. `example.com` or `blog.example.com`)
- `cert_arn` - Full ARN for an AWS Certificate Manager cert in the `us-east-1` region

## Outputs

- `cloudfront_domain` - `"${aws_cloudfront_distribution.site.domain_name}"`
- `cloudfront_hosted_zone_id` - `${aws_cloudfront_distribution.site.hosted_zone_id}"`
