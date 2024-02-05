# Update Route53 Dyndns
-----------------------
Use AWS Route53 as your own personal Dyndns

## Installation

1. Clone/Download this repo

1. Run `npm install`

1. Copy sample-config.json to config.json and edit it to fit your needs

1. Set the following environment variables AWS_REGION, AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY.
(Optionally also set the following environment variables if necessary: AWS_SESSION_TOKEN, AWS_CREDENTIAL_EXPIRATION)

1. Configure cron to run the `update` script periodically (eg. every 2 minutes)

## Description

This script updates your AWS Route53 zone records to your current public IP address.
It uses the whoami.cloudflare DNS service to detect your public IP address.
The address is cached in the `IpAddressFile` file (default: /var/tmp/route53-dyndns.txt).
If the address is different from the cached address your Route53 record(s) will be
updated with the new address.
