.PHONY: test lint

test: docker-plain/jenkinsfile_test.go go.mod go.sum
	go test -v github.com/opendevstack/ods-quickstarters/tests/docker-plain	

setup-tests: test-setup/main.go
	 go build -o test-setup.bin test-setup/main.go
	 ./test-setup.bin
	 ./scripts/setup-mocked-ods-repo.sh --ods-ref cicdtests
lint:
	echo "Checking code ..."
	golangci-lint run
