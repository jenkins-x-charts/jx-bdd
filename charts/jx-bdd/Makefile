CHART_REPO := gs://jenkinsxio/charts
NAME := jx-bdd

VERSION ?= 0.0.1

build: clean
	rm -rf Chart.lock
	helm dependency build
	helm lint

install: clean build
	helm install ${NAME} .

upgrade: clean build
	helm upgrade --install ${NAME} .

delete:
	helm delete ${NAME}

clean:
	rm -rf charts
	rm -rf ${NAME}*.tgz

release: clean
	sed -i -e "s/version:.*/version: $(VERSION)/" Chart.yaml

	helm dependency build
	helm lint
	helm package .
	helm repo add jx-labs $(CHART_REPO)
	helm gcs push ${NAME}*.tgz jx-labs --public
	rm -rf ${NAME}*.tgz%
