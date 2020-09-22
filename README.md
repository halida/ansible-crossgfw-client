# crossgfw-client

## Usage

Clone to your roles folder as `crossgfw-client`, then in your playbooks file:

```yaml
  roles:
    - role: crossgfw-client
      kcp_server: server
      ss_password: "{{ gfw.ss_password }}"
      kcp_password: "{{ gfw.kcp_password }}"
```

Start service:

```sh
systemctl --user start kcp
systemctl --user start sslocal-kcp
```

Testing:
```sh
curl -i -x socks5h://127.0.0.1:1082 http://www.twitter.com/
```
