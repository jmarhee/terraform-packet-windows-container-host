## Windows Node

A [Terraform](terraform.io) module for deploying a Windows Server node on [Packet](packet.com). This optionally configures Chocolatey, Docker, and handles an optional node reboot.

To create an instance, define a new instance as a module:

```
module "node_win" {
  source         = "./modules/windows_container_node"
  choco          = "${var.choco}"
  docker         = "${var.docker}"
  docker_restart = "${var.docker_restart}"
  node_name      = "windows-00"
  count          = "${var.count}"
  facility       = "${var.facility}"
  plan_primary   = "${var.plan_primary}"
  project_id     = "${var.project_id}"
}
```

and then apply:

```
terraform apply -target=module.instance_name
```

to manage that node's resources.
