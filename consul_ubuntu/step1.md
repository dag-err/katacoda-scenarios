
Open `server.hcl`{{open}} in the editor to inspect values required for a minimal configuration with the ACL system enabled.

#### Distribute configuration

`docker cp ./server.hcl volumes:/server/server.hcl`{{execute T1}}

### Start Consul server

Once configuration is distributed on the nodes, it is possible to start the Consul server.

`docker run \
    -d \
    -v server_config:/etc/consul.d \
    -p 8500:8500 \
    -p 8600:8600/udp \
    --name=server \
    consul agent -server -ui \
     -node=server-1 \
     -bootstrap-expect=1 \
     -client=0.0.0.0 \
     -config-file=/etc/consul.d/server.hcl`{{execute T1}}

### Check server logs

You can verify the Consul server started correctly by checking the logs.

`docker logs server`{{execute T1}}

Alternatively you can visit the [Consul UI](https://[[HOST_SUBDOMAIN]]-8500-[[KATACODA_HOST]].environments.katacoda.com/ui) tab to launch the Consul UI.

<div style="background-color:#fcf6ea; color:#866d42; border:1px solid #f8ebcf; padding:1em; border-radius:3px;">
  <p><strong>Warning: </strong>
  En guarde.
</p></div>