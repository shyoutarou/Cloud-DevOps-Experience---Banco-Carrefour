## Desafio

Desenhe uma organização de grupo de acessos e de uma organização utilizando o Draw.io e suba no seu github

## Utilizar ferramenta de diagramas:

O diagrams.net é um software de desenho gráfico multiplataforma gratuito e de código aberto desenvolvido em HTML5 e JavaScript. Sua interface pode ser usada para criar diagramas como fluxogramas, wireframes, diagramas UML, organogramas e diagramas de rede.

[Link diagrams.net](https://app.diagrams.net/)

## Resposta
<p align="center">
  <img src="../../../assets/Diagrama_Empresa.png" alt="Image" width="100%" />
</p>

## Modelo implemenação Terraform:

[Link modelo Terraform](github.com/digitalinnovationone/trilha-gcp-fundations-terraform-projetosfolders)

```bash
provider "google" {
  project = "anonima-project-node"
  region  = "us-central1"
  zone    = "us-central1-c"
  credentials = "${file("serviceaccount.yaml")}"
}

resource "google_folder" "Desenvolvimento" {
  display_name = "Desenvolvimento"
  parent       = "organizations/540829645030"
}

resource "google_folder" "Suporte" {
  display_name = "Suporte"
  parent       = "organizations/540829645030"
}

resource "google_folder" "DevOps" {
  display_name = "DevOps"
  parent       = "organizations/540829645030"
}


resource "google_folder" "Prod" {
  display_name = "Prod"
  parent       = google_folder.Desenvolvimento.name
}

resource "google_folder" "Test" {
  display_name = "Test"
  parent       = google_folder.Desenvolvimento.name
}

resource "google_folder" "QA" {
  display_name = "QA"
  parent       = google_folder.Suporte.name
}

resource "google_folder" "Prod" {
  display_name = "Prod"
  parent       = google_folder.DevOps.name
}

resource "google_folder" "Test" {
  display_name = "Test"
  parent       = google_folder.DevOps.name
}

resource "google_project" "anonima-dev-prod" {
  name       = "Desenvolvimento-Prod"
  project_id = "anonima-dev-prod"
  folder_id  = google_folder.Desenvolvimento.name
  auto_create_network=false
  billing_account = "018973-A8340F-83D8E5"
}


resource "google_project" "anonima-dev-test" {
  name       = "Desenvolvimento-Test"
  project_id = "anonima-dev-test"
  folder_id  = google_folder.Desenvolvimento.name
  auto_create_network=false
  billing_account = "018973-A8340F-83D8E5"
}

resource "google_project" "anonima-sup-qa" {
  name       = "Suporte-QA"
  project_id = "anonima-sup-qa"
  folder_id  = google_folder.Suporte.name
  auto_create_network=false
  billing_account = "018973-A8340F-83D8E5"
}

```


