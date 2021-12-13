# class 10

## <ins>*Jupyter Lab*

> web-based user interface for Project Jupyter, which is an open-source web application that allows data scientists to create and share documents that integrate live code, equations, computational output, visualizations, and other multimedia resources, along with explanatory text in a single document.

JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.) 


    install jupyterlab using pip 
```py
pip install jupyterlab
```

**Jupyter Docker Stacks**

set of ready-to-run Docker images containing Jupyter applications and interactive computing tools.

- Start a personal Jupyter Notebook server in a local Docker container

- Run JupyterLab servers for a team using JupyterHub

- Write your own project Dockerfile

after installing `docker` , use  the following command to pulls the jupyter/scipy-notebook image tagged 33add21fab64 from Docker Hub if it is not already present on the local host. It then starts a container running a Jupyter Notebook server and exposes the server on host port 8888. 

    docker run -p 8888:8888 jupyter/scipy-notebook:33add21fab64


## <ins>*Numpy*

    NumPy is a commonly used Python data analysis package. was originally developed in the mid 2000s, and arose from an even older package called Numeric.


we can use numpy package by importing it to our project

```py

import numpy as np

```

**Using NumPy To Read In Files**

 We can do this using the __numpy.genfromtxt__ function. 
 
 ```py

 text = np.genfromtxt("file.csv", delimiter=";", skip_header=1)

 ```



