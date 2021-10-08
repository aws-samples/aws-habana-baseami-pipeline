## AWS Habana Gaudi DL1 Base AMI Build Pipeline
To facilitate getting started with the Habana Gaudi DL1 instances. We have included some sample build scripts based on Packer to build base AL2, Ubuntu18.04, as well as ECS and EKS base AMIs. Included are sample buildspecs which you integrate with a CodeBuild/CodePipeline for automatic builds.

## Packer Instructions
In the `gaudi-ami_base` dir you will find packer scripts for Amazon Linux 2 and Ubuntu 18.04. Generally you just need to modify the `variables:{}` json and execute the packer build
````json
  "variables": {
    "region": "us-west-2",
    "flag": "ul18-base",
    "subnet_id": "subnet-4532e73d",
    "security_groupids": "sg-092c73af8b33e6bab",
    "build_ami": "ami-090717c950a5c34d3",
    "habanalabs-driver-version": "1.0.1-81"
  },
````  
After filling in the `variables` check that the packer script is validated.
````
packer validate habana-dl1-al2.yml
packer build habana-vt-al2.yml
````
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

This package depends on and may incorporate or retrieve a number of third-party
software packages (such as open source packages) at install-time or build-time
or run-time ("External Dependencies"). The External Dependencies are subject to
license terms that you must accept in order to use this package. If you do not
accept all of the applicable license terms, you should not use this package. We
recommend that you consult your company’s open source approval policy before
proceeding.

Provided below is a list of External Dependencies and the applicable license
identification as indicated by the documentation associated with the External
Dependencies as of Amazon's most recent review.

THIS INFORMATION IS PROVIDED FOR CONVENIENCE ONLY. AMAZON DOES NOT PROMISE THAT
THE LIST OR THE APPLICABLE TERMS AND CONDITIONS ARE COMPLETE, ACCURATE, OR
UP-TO-DATE, AND AMAZON WILL HAVE NO LIABILITY FOR ANY INACCURACIES. YOU SHOULD
CONSULT THE DOWNLOAD SITES FOR THE EXTERNAL DEPENDENCIES FOR THE MOST COMPLETE
AND UP-TO-DATE LICENSING INFORMATION.

YOUR USE OF THE EXTERNAL DEPENDENCIES IS AT YOUR SOLE RISK. IN NO EVENT WILL
AMAZON BE LIABLE FOR ANY DAMAGES, INCLUDING WITHOUT LIMITATION ANY DIRECT,
INDIRECT, CONSEQUENTIAL, SPECIAL, INCIDENTAL, OR PUNITIVE DAMAGES (INCLUDING
FOR ANY LOSS OF GOODWILL, BUSINESS INTERRUPTION, LOST PROFITS OR DATA, OR
COMPUTER FAILURE OR MALFUNCTION) ARISING FROM OR RELATING TO THE EXTERNAL
DEPENDENCIES, HOWEVER CAUSED AND REGARDLESS OF THE THEORY OF LIABILITY, EVEN
IF AMAZON HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. THESE LIMITATIONS
AND DISCLAIMERS APPLY EXCEPT TO THE EXTENT PROHIBITED BY APPLICABLE LAW.

## Dependencies

HabanaAI/Setup_and_Install (https://github.com/HabanaAI/Setup_and_Install) - Apache-2.0
