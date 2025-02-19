---
title: Create your own BIBBOX App
include_footer: true
draft: false
date: 2024-02-13T10:23:24+01:00
---

## Creating a BIBBOX App
Starting with an existing open-source software solution that handles data, one can easily transform it into a BIBBOX App, following the tutorial at [https://bibbox.readthedocs.io/en/latest/](https://bibbox.readthedocs.io/en/latest/).

Each BIBBOX App must be published in the [BIBBOX GitHub repository](https://github.com/bibbox), by creating a repository named _app-nameofapp_. The repository _app-template_ aims to guide users when creating an App.

<img class="aligncenter wp-image-627 size-large" src="/images/anatomyofanapp.png" alt="" width="525" height="385" />


Briefly, the most important components of a BIBBOX App are: 
- The **Base Docker** is a container created from a Docker Image of the existing software tool. The officially published Docker Image of the software can be used. If none is available, a Dockerfile of the Docker Image should be stored in a [BIBBOX GitHub repository](https://github.com/bibbox) named _img-nameofdocker_ and the Docker Image published in the [BIBBOX Docker Hub](https://hub.docker.com/u/bibbox/).
- **Additional Docker Containers** of the App, such as databases, can be integrated with the Docker Image of the Base Docker, resulting in a docker-compose file, which should be published in the _app-nameofapp_ repository. The Docker Images of the additional Docker Containers can, if necessary, be published in the [BIBBOX GitHub repository](https://github.com/bibbox) and in the [BIBBOX Docker Hub](https://hub.docker.com/u/bibbox/).
- The **FAIR Data Point** is recommended for Apps that handle data, in order to make the data FAIR. For the extension of an App with a [FAIR Data Point](/about/fair) (FDP), the different components of the FDP are combined into a Docker Image and published in the [BIBBOX Docker Hub](https://hub.docker.com/u/bibbox/). As many Apps do not internally support FDPs, the appropriate metadata of the App must be extracted and transformed by the middleware and then loaded into the FDP.

<img class="size-full wp-image-794 aligncenter" src="/images/build_app.png" alt="" width="733" height="214" />

## Understanding stakeholders
The following figure shows STAKEHOLDERS and DATA OBJECTS of a typical biobank. As a further step, every stakeholder and data object could have a unique ID. We would suggest distinguishing between:
<ul>
 	<li>Data objects directly related to a patient/donor.</li>
 	<li>Data objects generated by a study or medical event.</li>
 	<li>Data objects related to a sample or aliquot.</li>
</ul>
<img class="aligncenter size-full wp-image-185" src="/images/stakeholders.png" alt="" width="600" />