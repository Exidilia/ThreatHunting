in order to make this license server up and running, download the splunk licence server and put it in the same directory as the Dockerfile.
then run this command:

# safely build and run
```
docker build -t splunk-lic-srv:latest .
```
```
docker run -d \
  --name splunk-lic-srv \
  -p 3456:3456 \
  --read-only \
  --cap-drop=ALL \
  --security-opt=no-new-privileges:true \
  --memory="2g" \
  --cpus="1.0" \
  --tmpfs /tmp \
  --tmpfs /run \
  splunk-lic-srv:latest
```
[https://help.splunk.com/en/splunk-enterprise/administer/admin-manual/9.4/configure-splunk-licenses/configure-a-license-peer#id_70ae04bc_c933_4995_bb20_3d9bdde346ac__Configure_a_license_peer](url)
