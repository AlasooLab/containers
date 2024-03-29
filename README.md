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
or
```bash
docker build -t eqtlcatalogue/regenie:v3.2.1 .
```

### Build the container on an M1 Mac
```bash
docker buildx build --platform linux/amd64 --push -t quay.io/eqtlcatalogue/glimpse:1.1  .
```

### If needed, login to Quay.io
```bash
docker login quay.io
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
