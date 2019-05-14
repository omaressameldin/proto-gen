# Proto Gen
## How to use:
### 1. create a folder named `proto`
### 2. start container with a volume target --> `OUTPUT_PATH` and a volume src --> `[GO_APP_PATH]` and with these environment variables:
* `BUILD_PATH`  --> path of folder containing proto file which must start with `proto`
* `OUTPUT_PATH` --> location of folder to output `.pb.go` file
* `FILENAME` --> name of `proto3` file inside `BUILD_PATH`

### Example:
* `docker run [image_name] -e BUILD_PATH=/proto/v1 -e OUTPUT_PATH=/pkg/api/v1 -e FILENAME=upload.proto --mount type=bind,src=./app/pkg/service/v1,dst=/pkg/api/v1`