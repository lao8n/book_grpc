export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin

generate the server messages
// from server_streaming_rpc folder
protoc --go_out="/Users/nicholasdrake/Documents/grpc/nick_ch03/server_streaming_rpc/server/gen" "proto/order_management.proto"

generate the server 
protoc --go-grpc_out="/Users/nicholasdrake/Documents/grpc/nick_ch03/server_streaming_rpc/server/gen" "proto/order_management.proto"

// from server folder
go build -v -o bin/server
bin/server

generate the client messages
protoc --go_out="/Users/nicholasdrake/Documents/grpc/nick_ch03/server_streaming_rpc/client/gen" "proto/order_management.proto"

generate the client
protoc --go-grpc_out="/Users/nicholasdrake/Documents/grpc/nick_ch03/server_streaming_rpc/client/gen" "proto/order_management.proto"

// from client folder
go build -v -o bin/client
bin/client