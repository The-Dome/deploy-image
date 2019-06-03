# deploy-image

To run the container for packing docker images:
```bash
docker run -it -v /var/run/docker.sock:/var/run/docker.sock \
               --group-add $(getent group docker | cut -d: -f3) \
               -v $(pwd):/home/deploy/src \
               supastuff/deploy:latest
```

## Tools

* Ansible `ansible-playbook provision.yml --check`
* Packer `packer build pack.json`
* Terraform `terraform plan` `terraform apply`
* Docker (just for packer to build/tag/push)

## Todo

* Use Docker image as base image
