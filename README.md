## Overview
The **template-routeros-default** template adds to a stack the ability to provision the RouterOS development environment with a Docker container.

## Prerequisites
To use this template you need to use the `CLI` of `StackSpot` that you can download [**here**](https://stackspot.com/).

- Docker: ~20.10.8
- Docker Compose: ~3.8

## How to Use
### Input parameters
The inputs parameters needed to use the template are: 

| **Field**                     | **Value**         | **Description**   |
| :---                          | :---              | :---              |
| project_name                  | ex.: stackspot-routeros | Project name  |
| routeros_image_version       | ex.: latest       | RouterOS Docker Image Version |

 ## Creating the project from the template

 ```bash
stk create app project-name -S stack-routeros/default
 ```

## Execution of the created project

After creating your project, to build and run the docker containers solution, run the command below in the root of where you find the **docker-compose.yml** file

```bash
docker-compose -f 'docker-compose.yml' up --build
```

## Accessing the RouterOS interface

### List of exposed ports

| Description   | Ports | Mapped to
|---------------|-------|-----------
| SSH           | 22    | 12222
| WinBox        | 8291  | 18291

### Option 1 - Accessing via winbox
Download the latest version of winbox [by clicking here](https://mikrotik.com/download)

After downloading Winbox, run it.

| Field         | Example           |
|---------------|-------------------|
| Connect To    | localhost:18291   |
| Login         | admin             |
| Password      | ``In Blank``      |

Example:

![image](https://user-images.githubusercontent.com/135553/187108452-a666e9ee-6d8f-475f-b977-903f82db4905.png)

![image](https://user-images.githubusercontent.com/135553/187108527-b999d72f-852b-4b02-afde-862849722dd8.png)

### Option 2 - Running via the web interface
Then open http://localhost:8080 in your browser.

![image](https://user-images.githubusercontent.com/135553/187108595-b08a91f6-3e2f-46f1-a6ab-1160927bde65.png)

![image](https://user-images.githubusercontent.com/135553/187108642-c37f2c6d-00f1-41d5-8cac-a181d89187ed.png)


# References
- [Mikrotik RouterOS in Docker](https://github.com/EvilFreelancer/docker-routeros)