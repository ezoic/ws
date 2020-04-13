FROM golang:1.10.3-alpine3.7

RUN	apk add --no-cache git && \
	go get github.com/ezoic/httphead/... && \
	go get github.com/ezoic/pool/... 

COPY . /go/src/github.com/ezoic/ws
RUN go test -c -tags autobahn -coverpkg "github.com/ezoic/ws/..." github.com/ezoic/ws/example/autobahn

CMD ["./autobahn.test", "-test.coverprofile", "/report/server.coverage"]
