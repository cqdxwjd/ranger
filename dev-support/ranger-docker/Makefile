RANGER_VERSION=2.4.0
HADOOP_VERSION=3.3.6

ranger-base:
	docker buildx build \
		-t hub.hmf.xyz/emr/ranger-base:${RANGER_VERSION} \
		--platform linux/amd64 \
		-f Dockerfile.ranger-base .

ranger-hadoop:
	docker buildx build \
		--build-arg HADOOP_VERSION=${HADOOP_VERSION} \
        --build-arg RANGER_VERSION=${RANGER_VERSION} \
		-t hub.hmf.xyz/emr/ranger-hadoop:${HADOOP_VERSION} \
		--platform linux/amd64 \
		-f Dockerfile.ranger-hadoop .
	docker push hub.hmf.xyz/emr/ranger-hadoop:${HADOOP_VERSION}