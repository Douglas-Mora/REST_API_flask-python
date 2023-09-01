*Created virtual environment*
    Run `python -m venv .venv`.

Then, activate the venv. Locate the `activate.ps1` file, into .venv\Scripts\, copy the path and paste into the terminal to runt it, i.e.:
    `C:\Users\Lenovo\Documents\Programming_Coding\REST_API_flask-python\.venv\Scripts\activate.ps1`

*Install Flask*
    `pip install flas`

*To confirm the installation is correct, run...*
    `flask run`


*Docker*
A virtual machine is an emulation of an operating system.
i.e. a Windows VM running in a MacOS computer:

**------ VM example ------**
*Windows APP    Windows APP*
-------- Windows VM --------
-------- Hypervisor --------
---------- MacOS -----------
--------- Hardware ---------

**--------- Docker example ---------**
Container process    Container process
Container            Container
--------------- Docker ---------------
--------------- Linux ----------------
--------------- Hardware -------------

Both the Docker containers and the operating system use the Linux Kernel.

*What is a Kernel?*
It's an operating system made up of two main parts: the kernel and files/programs.
The kernel usually interacts with nand controls the hardware.


*What does a Docker container run?*
Everything but the kernel.
 - The OS is made up of kernel + applications
 - Any applications from the OS you want to use, need to be included in the container (i.e. Bash, curl, etc.).
 - I need to include Python, pip, and install dependencies your app needs.

Docker containers are based on images which specify what is inside the container when it runs.

*What is a Docker image?*
 - A snapshot of source code, libraries, dependencies, tools, and everything else (except the Operating System kernel) that a container needs to run.

*The Dockerfile*
 - A definition of a Docker image
 - We use Dockerfile to build images.
 - We can then use an image to run one or more containers.

**Dockerfile**
FROM python:3.10
EXPOSE 5000
WORKDIR /app
RUN pip install flask
COPY . .
CMD ["flask", "run", "--host", "0.0.0.0"]


*To run a container, run...*
    docker run -dp 5005:5000 <image_name>


