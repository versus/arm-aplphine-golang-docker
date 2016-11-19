## BUILD
```bash
docker build . -t armhf/golang:1.7.3
```
## RUN

```bash
docker run --rm  armhf/golang:1.7.3 sh -c "go get github.com/golang/example/hello/... && exec hello"
```
## Installing in our system

```bash
docker run --rm  -v /tmp/bin:/go/bin armhf/golang:1.7.3  sh -c "go get github.com/golang/example/hello/..." && /tmp/bin/hello
```

### Cross-compilation

```bash
docker run -e GOOS=darwin -e GOARCH=amd64 -v /tmp/crosstest:/go/bin  armhf/golang:1.7.3  sh -c "go get github.com/golang/example/hello/..."
```

```bash
docker run -e GOOS=linux -e GOARCH=amd64 -v /tmp/crosstest:/go/bin  armhf/golang:1.7.3  sh -c "go get github.com/golang/example/hello/..."
```

```bash
docker run -e GOOS=windows -e GOARCH=amd64 -v /tmp/crosstest:/go/bin  armhf/golang:1.7.3  sh -c "go get github.com/golang/example/hello/..."
```
