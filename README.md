# Introduction
Using the Hashicorp docker (light) image: https://hub.docker.com/r/hashicorp/terraform/

(The full image contains git plus all the source code)

Create an `ssh` directory and generate a key:
```
$ ssh-keygen -t rsa -C "insecure-deployer" -P '' -f ssh/insecure-deployer
```

# AWS Credentials
Create a file in the project root called `terraform.tfvars` containing
```
access_key = "foo"
secret_key = "bar"
```

# Running terraform
```
docker run -v $PWD:/data --workdir=/data -i -t hashicorp/terraform:light plan
```

```
docker run -v $PWD:/data --workdir=/data -i -t hashicorp/terraform:light apply
```
