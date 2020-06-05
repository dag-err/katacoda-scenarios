
You can now use the bootstrap token to create other ACL policies for the rest of your datacenter.

The first policy you are going to create is for the server.

Open the `server_policy.hcl`{{open}} file to review the policy.

Create the policy and token with the `consul acl` command.

`consul acl policy create \
  -name consul-server-one \
  -rules @server_policy.hcl`{{execute T1}}


`consul acl token create \
  -description "consul-server-1 agent token" \
  -policy-name consul-server-one | tee server.token`{{execute T1}}

<div style="background-color:#fcf6ea; color:#866d42; border:1px solid #f8ebcf; padding:1em; border-radius:3px;">
  <p><strong>Warning: </strong>
  En guarde.
</p></div>

Finally you can apply the token to the server as its `agent` token.

`consul acl set-agent-token agent $(cat server.token  | grep SecretID  | awk '{print $2}')`{{execute T1}}