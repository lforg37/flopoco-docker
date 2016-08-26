# Flopoco dockerfile

This Dockerfile allow the containarisation of [FloPoCo](http://flopoco.gforge.inria.fr/), a « generator of arithmetic cores (Floating-Point Cores, but not only) for FPGAs (but not only).»

## Building the docker image
1. clone this repository
2. Go into the `docker_build` repository
```
cd docker_build
```
3. Build the docker image
```
docker build -t flopoco .
```

## Setting a bash alias

Set the following alias (you might want to put that line in your .bashrc) :
```
alias flopoco="docker run -v $PWD:/flopoco_workspace flopoco"
```

### Enabling bash autocompletion

Execute the following command and follow it's indications :
```
flopoco BuildAutocomplete
```
