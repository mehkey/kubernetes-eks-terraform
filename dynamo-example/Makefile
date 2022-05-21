.phony: build push

all: build push 
CMD := $(aws ecr get-login-password --region us-west-2 | docker login --username AWS --password-stdin 041835826865.dkr.ecr.us-west-2.amazonaws.com)

build:
	docker build -t mehkey/eks-dynamo .

push: 
	${CMD}
	docker tag mehkey/eks-dynamo:latest 041835826865.dkr.ecr.us-west-2.amazonaws.com/mehkey/eks-dynamo:latest
	docker push 041835826865.dkr.ecr.us-west-2.amazonaws.com/mehkey/eks-dynamo:latest

