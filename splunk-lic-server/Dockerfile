# Use the scratch base image for a minimal container
FROM alpine

# Copy the binary into the image
COPY dvt-splunk_licsrv.1.0.linux.amd64 /dvt-splunk_licsrv.1.0.linux.amd64

# Make the binary executable (not necessary if it's already executable)
RUN chmod +x dvt-splunk_licsrv.1.0.linux.amd64

# Set the entrypoint to run the binary
ENTRYPOINT ["./dvt-splunk_licsrv.1.0.linux.amd64","-port","3456","-host","0.0.0.0"]
