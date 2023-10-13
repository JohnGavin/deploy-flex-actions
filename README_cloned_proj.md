# https://github.com/JohnGavin/deploy-flex-actions#setting-environment-with-rstudio-server

docker-compose up -d
docker-compose down
docker ps

export FLEX_IMAGE=rkrispin/flex_dash_env:dev.0.0.0.9000
export TUTORIAL_WORKING_DIR=/Users/johngavin/Documents_GitHub/deploy-flex-actions
export RSTUDIO_CONFIG_PATH=/Users/johngavin/.config/rstudio
docker run -d -p 8787:8787 \
	-v $TUTORIAL_WORKING_DIR:/home/rstudio/flexdash \
	-v $RSTUDIO_CONFIG_PATH:/home/rstudio/.config/rstudio \
	$FLEX_IMAGE


docker stop 19d1042b3f9b
docker rm 19d1042b3f9b
docker ps

