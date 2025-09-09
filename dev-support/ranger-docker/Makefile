RANGER_VERSION=2.4.0
HADOOP_VERSION=3.3.6
SOLR_VERSION=8
RANGER_DB_TYPE=mysql

ranger-base:
	docker buildx build \
		-t hub.hmf.xyz/emr/ranger-base:${RANGER_VERSION} \
		--platform linux/amd64 \
		-f Dockerfile.ranger-base .
	docker push hub.hmf.xyz/emr/ranger-base:${RANGER_VERSION}

ranger-hadoop:
	docker buildx build \
		--build-arg HADOOP_VERSION=${HADOOP_VERSION} \
        --build-arg RANGER_VERSION=${RANGER_VERSION} \
		-t hub.hmf.xyz/emr/ranger-hadoop:${HADOOP_VERSION} \
		--platform linux/amd64 \
		-f Dockerfile.ranger-hadoop .
	docker push hub.hmf.xyz/emr/ranger-hadoop:${HADOOP_VERSION}

ranger-solr:
	docker buildx build \
		-t hub.hmf.xyz/emr/ranger-solr:${SOLR_VERSION} \
		--platform linux/amd64 \
		-f Dockerfile.ranger-solr .
	docker push hub.hmf.xyz/emr/ranger-solr:${SOLR_VERSION}

ranger:
	docker buildx build \
		-t hub.hmf.xyz/emr/ranger:${RANGER_VERSION} \
		--build-arg RANGER_DB_TYPE=${RANGER_DB_TYPE} \
		--build-arg RANGER_VERSION=${RANGER_VERSION} \
		--platform linux/amd64 \
		-f Dockerfile.ranger .
	docker push hub.hmf.xyz/emr/ranger:${RANGER_VERSION}