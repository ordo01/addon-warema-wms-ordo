REGISTRY := ghcr.io/ol-iver
VERSION	 := v$(shell date +'%Y%m%d')-$(shell git rev-parse --short HEAD)


.PHONY: docker-images
docker-images:
	@echo "Building docker images with version and tag $(VERSION)"
	docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7,linux/arm/v6 -t $(REGISTRY)/warema-bridge:$(VERSION) -t $(REGISTRY)/warema-bridge:latest -f warema-bridge/Dockerfile warema-bridge/

.PHONY: docker-push
docker-push:
	@echo "Pushing docker images with version and tag $(VERSION)"
	docker buildx build --push --platform linux/amd64,linux/arm64,linux/arm/v7,linux/arm/v6 -t $(REGISTRY)/warema-bridge:$(VERSION) -t $(REGISTRY)/warema-bridge:latest -f warema-bridge/Dockerfile warema-bridge/