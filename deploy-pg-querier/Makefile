WASH := wash

CONFIG_NAME := default-postgres
POSTGRES_HOST := postgres
POSTGRES_PORT := 5432
POSTGRES_USERNAME := postgres
POSTGRES_PASSWORD := p05tgr3$
POSTGRES_DATABASE := public
POSTGRES_TLS_REQUIRED := false

APP_FILE := wadm.yaml

CALL_NAME := rust_sqldb_postgres_query-querier
MODULE := wasmcloud:examples/invoke.call

.PHONY: config-put deploy-app call-service

config-put:
	$(WASH) config put $(CONFIG_NAME) \
        POSTGRES_HOST=$(POSTGRES_HOST) \
        POSTGRES_PORT=$(POSTGRES_PORT) \
        POSTGRES_USERNAME=$(POSTGRES_USERNAME) \
        POSTGRES_PASSWORD=$(POSTGRES_PASSWORD) \
        POSTGRES_DATABASE=$(POSTGRES_DATABASE) \
        POSTGRES_TLS_REQUIRED=$(POSTGRES_TLS_REQUIRED)

deploy-app:
	$(WASH) app deploy --replace $(APP_FILE)

call-service:
	$(WASH) call $(CALL_NAME) $(MODULE)
