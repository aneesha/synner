# Synner

Synner is a tool that helps users generate real-looking synthetic data by visually and declaratively specifying the 
properties of the dataset such as each field’s statistical distribution, its domain, and its relationship to other fields. 
It provides instant feedback on every user interaction by updating multiple visualizations of the generated dataset and 
even suggests data generation specifications from a few user examples and interactions. Synner visually communicates 
the inherent randomness of statistical data generation. 
<br/><br/>
![screenshot](https://github.com/huda-lab/synner/blob/resources/synner-ui-sigmod.png)

**Note:** This is a **fork** of https://github.com/huda-lab/synner which includes a Dockerfile (to build and run) and additional installation instructions (i.e. you need to run bower to download additional javascript dependencies). 

## Publications

**[Is this Real? Generating Synthetic Data that Looks Real](https://dl.acm.org/doi/10.1145/3332165.3347866)**
<br/>
<span style="font-size:80%">Miro Mannino, Azza Abouzied - UIST'19</span>

**[Synner: Generating Realistic Synthetic Data](https://dl.acm.org/doi/abs/10.1145/3318464.3384696)**
<br/>
<span style="font-size:80%">Miro Mannino, Azza Abouzied - SIGMOD'20</span>

## Videos

[Short video version](https://youtu.be/ez2Tge5Bf2M)

[Extended video version](https://youtu.be/BH9tiuoayp0)

[SIGMOD'20 - Demo session](https://youtu.be/6W99fj9bB0U)

## Repository Content

This repository contains:

Synner's source code, the datasets that were used in the publication and a Dockerfile to run locally.

## How to run Synner

Synner can be run as a server, which also provides the user interface, or as a command line interface application.

### Running the user interface in a local Docker container

You will need Docker and npm installed.

1. Clone the repo
```
  $ git clone https://github.com/aneesha/synner.git
```
2. Install Bower and then install the required javascript dependencies
```
  $ cd synner/synner-server/src/main/resources/static
  $ npm install bower -g
  $ bower install
```
3. Build the docker image 
```
  $ docker image build -t docker-synner .
```
4. Run the docker container
```
  $ docker container run -p 5000:5000 docker-synner
```
5. Go to http://localhost:5000 in a web browser


### Running the server

Synner server can be run by launching the main static method in `edu.nyu.dtl.synner.SynnerServerApplication`

This method will run Synner's server as a Spring Boot application in the port 5000


### Command line interface

Synner can be launched from the command line interface with Java by using the main static method in 
class `edu.nyu.dtl.synner.core.Main`

This method accepts a path of a CSV file as console argument, where specifications are written. For example:

```
  java -classpath "..." edu.nyu.dtl.synner.core.Main my-specifications.json
```
