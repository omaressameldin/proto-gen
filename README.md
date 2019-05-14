# Proto Gen
## How to use:
### start container with these volumes:
* volume for directory `BUILD_PATH` that has `proto3` file
* volume for directory `OUTPUT_PATH` that should have `.pb.go` file inside a golang app
### and with these environment variables:
* `BUILD_PATH`  --> path of directory containing proto file which must start with `proto`
* `FILENAME` --> name of `proto3` file inside `BUILD_PATH`
* `OUTPUT_PATH` --> location of folder to output `.pb.go` file

## Example:
```
docker run omaressameldin/proto-gen \
-e BUILD_PATH=/proto \
-e FILENAME=upload.proto \
-e OUTPUT_PATH=/pkg/api/v1 \
--mount type=bind,src=./proto,dst=/proto` \
--mount type=bind,src=./app/pkg/service/v1,dst=/pkg/api/v1
```