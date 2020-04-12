export IMAGE_NAME={{ cookiecutter.prjName }}-image
export CONTAINER_NAME={{ cookiecutter.prjName}}-container
export JUPYTER_HOST_PORT=8888
export DOCKERFILE=Dockerfile

create-image:
	docker build \
		-t $(IMAGE_NAME) \
		-f (DOCKERFILE)


create-container:
	docker run \
		-it \
		-v $(PWD):/work \
		-p $(JUPYTER_HOST_PORT): 8888 \
		--name $(CONTAINER_NAME) \
		$(IMAGE_NAME)

clean: clean-container clean-image

clean-container:
	docker rm $(CONTAINER_NAME)

clean-image:
	docker image rm $(IMAGE_NAME)

jupyter:
	jupyter lab \
		--ip=0.0.0.0 \
		--allow-root \
		--NotebookApp.token=''

