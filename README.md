## To deploy lambda layer Cloudformation stack to AWS

```
npm ci
npm run setup
```

## To teardown Cfn stack
```
npm run teardown
```

## How the psql binaries came about

- From an Amazon Linux 2 VM
```
sudo amazon-linux-extras install postgresql14
ldd `which psql` | awk '{print $3}' > out.txt
zip archive -@ < out.txt

cp archive.zip path/to/folder/layer
cd path/to/folder/layer
unzip archive.zip
rm archive.zip
```

## refs:
- https://www.serverless.com/blog/publish-aws-lambda-layers-serverless-framework/
- https://github.com/serverless/examples/tree/master/aws-ffmpeg-layer

