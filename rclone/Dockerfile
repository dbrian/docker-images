FROM golang:alpine as builder
RUN apk --no-cache add git \
 && go get github.com/ncw/rclone

FROM alpine
RUN apk --no-cache add fuse
COPY --from=builder /go/bin/rclone /usr/bin/rclone
ENTRYPOINT ["rclone"]
