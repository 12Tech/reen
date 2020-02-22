.PHONY: clean build

STACK_NAME = reen-development

build:
	GOOS=darwin GOARCH=amd64 go build -o hello-world/hello-world ./hello-world

clean:
	rm -rf ./hello-world/hello-world
	rm -f tpl.yml

package:
	sam package --s3-bucket ${DEPLOYMENT_BUCKET} > tpl.yml

deploy:  package
	sam deploy --template-file tpl.yml --stack-name ${STACK_NAME} --capabilities CAPABILITY_IAM
	rm -f tpl.yml
