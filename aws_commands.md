# after creating aws account and IAM user with appropiate credentials

## login
aws ecr get-login-password --region "your time-zone" | docker login --username AWS --password-stdin "your user id".dkr.ecr.eu-central-1.amazonaws.com

## tag the image to "connect" with privat repository on AWS
docker tag <image-id> <repository-url>:<tag>

## push the image to the repository
docker push <image-id> <repository-url>:<tag>

## making changes/version control
docker build -t my-app:1.1 .

## to rename image
docker tag <use the same command but change the idtag -- my-app:1.1>


