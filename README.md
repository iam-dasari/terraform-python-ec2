### 0 20 ? * MON-FRI *

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents"
      ],
      "Resource": "arn:aws:logs:*:*:*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "ec2:Start*",
        "ec2:Stop*",
        "ec2:Describe*"
      ],
      "Resource": "*"
    }
  ]
}

### What this policy allows
| Service         | Actions           | Purpose                       |
| --------------- | ----------------- | ----------------------------- |
| CloudWatch Logs | `CreateLogGroup`  | Create log groups             |
| CloudWatch Logs | `CreateLogStream` | Create log streams            |
| CloudWatch Logs | `PutLogEvents`    | Write logs                    |
| EC2             | `Start*`          | Start EC2 instances           |
| EC2             | `Stop*`           | Stop EC2 instances            |
| EC2             | `Describe*`       | View EC2 resource information |

Note: ec2:Start*, ec2:Stop*, and ec2:Describe* use wildcards, so they grant multiple matching EC2 actions. For production, you would normally narrow permissions to the specific actions and resources required.