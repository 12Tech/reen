.PHONY: clean build

STACK_NAME = reen-development

build:
	GOOS=linux GOARCH=amd64 go build -o hello-world/hello-world ./hello-world

clean:
	rm -rf ./hello-world/hello-world

deploy:
	sam deploy \
		--s3-bucket ${DEPLOYMENT_BUCKET} \
		--stack-name ${STACK_NAME} \
		--capabilities CAPABILITY_IAM