
First, you will configure your environment to be able to interact with the Consul agent.

`export CONSUL_HTTP_ADDR=localhost:8500`{{execute T1}}

### Bootstrap ACLs

You need to bootstrap the ACL system to start using ACLs.

Run `consul acl bootstrap | tee consul.bootstrap`{{execute T1}} to bootstrap the ACL system, generate your first token, and capture the output into the `consul.bootstrap` file.

If you receive an error saying "The ACL system is currently in legacy mode.", this indicates that the Consul service is still starting. Wait a few seconds and try the command again.

<div style="background-color:#fcf6ea; color:#866d42; border:1px solid #f8ebcf; padding:1em; border-radius:3px;">
  <p><strong>Warning: </strong>
  En guarde.
</p></div>


