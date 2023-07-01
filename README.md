#provider plugin
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "3.0.2"
    }
  }
}
#provider info
provider "docker" {
  host = "unix:///var/run/docker.sock"
}
#resource block
resource "docker_image" "ubuntu" {
  name = "ubuntu:latest"
}
resource "docker_image" "jenkins" {
  name = "jenkins:jenkins"
}
resource "docker_image" "tomcat" {
  name = "tomcat:latest"
}
