# Matrix

Matrix�� �ǽð� ���뿡 �־ �⺻���� ���ȹ���̴�. Opsdroid�� ���� Matrix connector�� ��κ��� �̺�Ʈ �ۼ��ŵ��� ����Ѵ�.

## Requirements

�� Connector�� ����ϱ� ���ؼ� ������ �ʿ��ϴ�.
-	Bot�� ���� matrix ���� ���̵� ��й�ȣ�� �ʿ��ϴ�.
-	����� home server�� �˾ƾ��Ѵ�.[homeserver](https://matrix.org/faq/#what-is-a-homeserver%3F)
-	��� room�� �ּҸ� �˾ƾ��Ѵ�.


## Configuration
������ configuration�� ������ ����.

```yaml
connectors:
  matrix:
    # Required
    mxid: "@username:matrix.org"
    password: "mypassword"
    rooms:
      'main': '#matrix:matrix.org'
    # Optional
    homeserver: "https://matrix.org"
    nick: "Botty McBotface"  # The nick will be set on startup
```

Connector�� �̸��� ���� ���̶�� �� ���� ������ �� �ִ�. ù��° ���� �̸��� ������ ��main���̾�� �Ѵ�. Configuration options ��� ������ ������ ����.


```yaml
connectors:
  matrix:
    # Required
    mxid: "@username:matrix.org"
    password: "mypassword"
    # A dictionary of rooms to connect to
    # One of these have to be named 'main'
    rooms:
      'main': '#matrix:matrix.org'
      'other': '#element-web:matrix.org'
    # Optional
    homeserver: "https://matrix.org"
    nick: "Botty McBotface"  # The nick will be set on startup
    room_specific_nicks: False  # Look up room specific nicknames of senders (expensive in large rooms)
    device_name: "opsdroid"
    enable_encryption: False
    device_id: "opsdroid" # A unique string to use as an ID for a persistent opsdroid device
    store_path: "path/to/store/" # Path to the directory where the matrix store will be saved
```


## End to End Encryption

E2EE�� ����ϱ� ���ؼ� ��olm�� ���̺귯���� �ʿ��ϴ�. Pip ��ġ�δ� �Ұ����ϰ� ���� ��ũ���� �ٿ�ε� �����ϴ�. (https://gitlab.matrix.org/matrix-org/olm/) olm�� ��ġ�� �������� opsdroid�� connector_matrix_e2e�� �ٿ�ε� �ؾ��Ѵ�. �̴� �⺻������ �ٿ�ε� �Ǵ� ������ �ƴ϶� ������ �ٿ�ε尡 �ʿ��ϴ�. �߰������� enable_encryption : True�� �����ؾ��Ѵ�. �� Connector�� E2EE�� �����Ѵ�.