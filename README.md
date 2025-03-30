## Python Simple
This is the first application that is python and starts up a [FastAPI](https://fastapi.tiangolo.com/) server

## Environment
AWS keys are required to use the `aws cli`. The ketys can be retrieved from the IAM dashboard. Export the environment variables:
```bash
export AWS_ACCESS_KEY_ID=xxxxxxxxx  (this is the access key from IAM)
export AWS_SECRET_ACCESS_KEY=yyyyyyyyyy (this is the secret key from IAM)
```

## Docker
### Loging into the docker repository
```bash
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 594709136083.dkr.ecr.us-east-1.amazonaws.com
```
### Build the image locally
```bash
docker build -t python/pythonfirst .
```
### Tag the image with ECR
```bash
docker tag python/pythonfirst 594709136083.dkr.ecr.us-east-1.amazonaws.com/python/pythonfirst:latest
```
### Push the image to the ECR repo
```bash
docker push 594709136083.dkr.ecr.us-east-1.amazonaws.com/python/pythonfirst:latest
```
