export GOOGLE_APPLICATION_CREDENTIALS=../service-account.json
export GCP_PROJECT=
export SERVICE_NAME=
export SERVICE_PORT=8080
export SERVICE_ACCOUNT_EMAIL=service@your-project.iam.gserviceaccount.com'
export PUSH_NOTIFICATION_TOPIC=PushNotification
export PUBSUB_API_KEY=dev
export MINIFLUX_HOST=
export MINIFLUX_USER=
export MINIFLUX_PASS=


run:
	go build -o server; ./server

test:
	go test -cover

gcloud-deploy:
	gcloud config set project $(GCP_PROJECT)
	gcloud builds submit \
	--config clouddeploy.yml \
	--substitutions=_SERVICE_NAME=$(SERVICE_NAME)\
	,_SERVICE_ACCOUNT_EMAIL=$(SERVICE_ACCOUNT_EMAIL)\
	,_PUSH_NOTIFICATION_TOPIC=$(PUSH_NOTIFICATION_TOPIC)\
	,_PUBSUB_API_KEY=$(PUBSUB_API_KEY)\
	,_MINIFLUX_HOST=$(MINIFLUX_HOST)\
	,_MINIFLUX_USER=$(MINIFLUX_USER)\
	,_MINIFLUX_PASS=$(MINIFLUX_PASS)