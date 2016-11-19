# BUILD
docker build . -t armhf/golang:1.7.3
# RUN
docker run --rm  armhf/golang:1.7.3 sh -c "go get github.com/golang/example/hello/... && exec hello"
