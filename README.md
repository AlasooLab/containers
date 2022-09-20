# containers

The eQTL Catalogue repository of containers at [quay.io](https://quay.io/user/eqtlcatalogue).

### Go into container directory (where Dockerfile is located)
```bash
cd regenie
```

### Build the Docker container
```bash
sudo docker build -t eqtlcatalogue/regenie:v3.2.1 .
```


### Tag the container for Quay.io
```bash
docker tag eqtlcatalogue/regenie:v3.2.1 quay.io/eqtlcatalogue/regenie:v3.2.1
```

### Push the container to Quay.io
```bash
docker push quay.io/eqtlcatalogue/regenie:v3.2.1
```

### Build a local copy of the Singularity container
```bash
singularity build regenie.img docker://quay.io/eqtlcatalogue/regenie:v3.2.1
```
