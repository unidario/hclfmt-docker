# hclfmt on docker

[hclfmt][1] is a command to format and prettify HCL (HashiCorp configuration language) files.  
I didn't write hclfmt. It was written by [Fatih Arslan][2].

## Run docker container
There are two modes.  

1. Overwrite `${PWD}/job.nomad` with formatted output:
```
docker run --rm -v ${PWD}/job.nomad:/src/job.nomad unidario/hclfmt:latest -w job.nomad
```
2. Print formatted output of `${PWD}/job.nomad` to stdout:  
```
docker run --rm -v ${PWD}/job.nomad:/src/job.nomad unidario/hclfmt:latest job.nomad
```

## Build docker image locally
```
git clone https://github.com/unidario/hclfmt-docker.git
cd hclfmt-docker
docker build -t hclfmt:latest .
```


[1]: https://github.com/fatih/hclfmt/
[2]: https://github.com/fatih
