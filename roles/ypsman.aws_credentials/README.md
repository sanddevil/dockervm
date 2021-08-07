ansible aws-credentials
=======================
[![Build Status](https://travis-ci.org/ypsman/ansible-aws-credentials.svg?branch=master)](https://travis-ci.org/ypsman/ansible-aws-credentials)

AWS Credentials, Region and Config for specific User.


Example Playbook
----------------

    - hosts: all
      roles:
        - role: ypsman.aws-credentials
          aws_user: 'username'
          aws_userhome: '/home/username'
          aws_region: 'eu-central-1'
          aws_key_id: 'youreAWSkey'
          aws_secret: 'youreAWSsecret'

