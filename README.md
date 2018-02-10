# Application
[Minio](https://github.com/minio/minio)

# Description
Minio is an object storage server released under Apache License v2.0. It is compatible with Amazon S3 cloud storage service. It is best suited for storing unstructured data such as photos, videos, log files, backups and container / VM images. Size of an object can range from a few KBs to a maximum of 5TB.

# Access application
`http://<host ip>:9000`

# Run the application
The ```PUID``` and ```PGID``` values are not necessary for unRAID 6.
## Usage
Please replace all user variables in the below command defined by ```<>``` with the correct values.
```
docker run -d \
  --name=<container name> \  
  -p <port>:9000 \
  -e PUID=<uid for user> \
  -e PGID=<gid for user> \
  -v /path/to/data:/export \
  tyler43636/unraid-minio
```

## Example
```
docker run -d \
  --name=minio \
  -p 9000:9000 \
  -e PUID=99 \
  -e PGID=100 \
  -v /data:/export \
  tyler43636/unraid-minio
```

# Notes
User ID (PUID) and Group ID (PGID) can be found by issuing the following command for the user you want to run the container as:
```
id <username>
```
