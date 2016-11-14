---
title: Terraform Pitfalls
---
# Terraform Pitfalls

Terraform, as a tool, is pretty darn good at helping you provision code in a format that is easy to understand, easy to maintain, and lets you get back to doing what you want to do: code.

#### Oops, I Now Have a $50,000 Amazon Bill

Don't put your AWS access and secret keys in your repositories. I cannot stress this enough. Public, private, does not matter. Don't put them there.

What's nice about Terraform, is that when combined with the AWS CLI SDK, you can easily configure your system without having to worry about accidentally uploading your private information onto the web.

For instance, most of the time you start with this:

```
provider "aws" {
    access_key = "YOUR_ACCESS_KEY"
    secret_key = "YOUR_SECRET_KEY"
    region = "us-east-1"
}
```

When you inevitably upload this file (and you will, trust me), you will likely find yourself on the wrong end of Amazon Billing trying to resolve what exactly just happened.
