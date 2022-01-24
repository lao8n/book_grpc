https://stackoverflow.com/questions/60578892/protoc-gen-go-grpc-program-not-found-or-is-not-executable

brew install protobuf
go install google.golang.org/protobuf/cmd/protoc-gen-go
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
protoc --go_out=plugins=grpc:. *.proto

change .proto file to include
option go_package = "./";

generate the messages
protoc --go_out="/Users/nicholasdrake/Documents/grpc/nick_ch02/productinfo/service/ecommerce" -I "ecommerce" "ecommerce/product_info.proto"

protoc --go_out="/Users/nicholasdrake/Documents/grpc/nick_ch02/productinfo/service/ecommerce" "proto/product_info.proto"


generate the services
protoc --go-grpc_out="/Users/nicholasdrake/Documents/grpc/nick_ch02/productinfo/service/ecommerce" -I "ecommerce" "ecommerce/product_info.proto"

generate the client
protoc --go-grpc_out="/Users/nicholasdrake/Documents/grpc/nick_ch02/productinfo/client/ecommerce" -I "ecommerce" "ecommerce/product_info.proto"
