export BUCKET_NAME ?= test
export AWS_REGION ?= ap-southeast-2

COMPOSE_RUN_AWS = docker-compose run --rm aws

create_bucket:
	@echo "Creating new S3 bucket: " $(BUCKET_NAME)
	$(COMPOSE_RUN_AWS) make _create_bucket

_create_bucket:
	bash scripts/create_bucket.sh

delete_bucket:
	@echo "Deleting S3 bucket: " BUCKET_NAME
	$(COMPOSE_RUN_AWS) make _delete_bucket

_delete_bucket:
	bash scripts/delete_bucket.sh

.PHONY: clean
clean:
	docker-compose down --remove-orphans