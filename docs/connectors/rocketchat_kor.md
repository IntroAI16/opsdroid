# Rocket.Chat

Rocket.Chat�� ���� Connector.[Rocket.Chat](https://rocket.chat).

## Requirements

 * Rocket.Chat ������ �����ϰ� ����� server�� chat service�� ���ε��Ѵ�.[Rocket.Chat](https://open.rocket.chat/home) 
 * Personal Access Token�� �����ϰ� ���� ������ ���� �ִ´�.


## Configuration

```yaml
connectors:
  rocketchat:
    # required
    user-id: "1ioKHDIOD"
    token: "zyxw-abdcefghi-12345"
    # optional
    bot-name: "mybot" # default "opsdroid"
    default-room: "random" # default "general"
    group: "MyAwesomeGroup" # default to None
    channel-url: "http://127.0.0.1" # defaults to https://open.rocket.chat
    update-interval: 5 # defaults to 1
```

_Notes:_

-	Opsdroid�� ���ÿ� �� �ϳ��� channel�� �׷���� ���븸 �����ϴ�.
-	�׷��� private�ϴ� 
-	�������� ��ſ��� ä�κ��� ������ �ִ�.
-	ä���� �̸��� #���� ��������.
-	Opsdroid�� �޽����� ���ŵǸ� ����ؼ� ä�ü����� ������ �����Ѵ�. ����� �� ���� �ֱ⸦ update-interval�� ���� ������ �����ϴ�. Opsdroid�� ���������� ������ �޽����� �бⰡ �����ϴ�.



## Usage


```
FabioRosado Owner 6:11 PM
hi

opsdroid @FabioRosado Owner 6:11 PM
Hi FabioRosado
```

�� ���� ������ �������� opsdroid�� Rocket.Chat�� ���ؼ� ������ ���̴�. hi��� Ÿ���� �ߴ��� �Ŀ� ������� ���� �̸��� �ٰԵȴ�. �̴� ���Ἲ�� �׽�Ʈ�ϴ� �������� �ٰ� �Ǵ� ���̴�. �̰��� ������� �Ͽ��� �ϳ��� �������� opsdroid�� �����ϰ� bot-name�� ����ؼ� �ٲ� ���̴�.
