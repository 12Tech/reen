.PHONY: clean build

STACK_NAME = reen-development

build:
	GOOS=darwin GOARCH=amd64 go build -o hello-world/hello-world ./hello-world

clean:
	rm -rf ./hello-world/hello-world

deploy:
	sam package --s3-bucket ${DEPLOYMENT_BUCKET} | sam deploy --template-file - --stack-name ${STACK_NAME} --capabilities CAPABILITY_IAM