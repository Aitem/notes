## Allow ssh access throw key

``` sh
ssh-keygen
cat __your_pub_key__ >> ~/.ssh/authorized_keys

add to config

  IdentitiesOnly yes
  IdentityFile ~/.ssh/miac/your_key

```

