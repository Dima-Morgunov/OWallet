# Compile Binary Step
FROM golang:1.22.5 as builder

WORKDIR /workspace
COPY . .
RUN make build

# Service Container
FROM scratch

COPY --from=builder /workspace/bin/server .
COPY data data
COPY pages pages

CMD ["./server"]