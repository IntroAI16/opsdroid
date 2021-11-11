# Mattermost connector

Mattermost�� ���� connector [Mattermost](https://mattermost.com/).

## Requirements

-	Mattermost ����
-	Mattermost bot ����(https://docs.mattermost.com/developer/bot-accounts.html).
  * Mattermost bot�� ���� �����Ѵ�.(https://docs.mattermost.com/developer/bot-accounts.html).
  * Bot Account Access Token���� Ŭ���ؼ� atoken�� �߱� �޴´�.

## Configuration

```yaml
connectors:
  mattermost:
    # Required
    token: "zyxw-abdcefghi-12345"
    url: "mattermost.server.com"
    team-name: "myteam"
    # Optional
    scheme: "http" # default: https
    port: 8065 # default: 8065
    ssl-verify: false # default: true
    connect-timeout: 30 # default: 30
```

## Usage
Connector�� ���θ����δ� opsdroid�� ����� ���� ������� ���Ѵ�. Mattermost�� ���� �Ǿ ����ڴ� ����ؼ� opsdroid�� ���� �����鼭 ���� �ؾ��Ѵ�.
���� ���Ե� opsdroid�� ��� ��ɵ��� �����Ѵ�. ����� opsdroid�� �����ϸ� �� ��ɵ��� �� �� �ִ�.
Opsdroid�� ä�ù濡�� Ȱ��ȭ ���� ������ �ʴ� ������ ���̳� ä�η� �ʴ밡 �����ϴ�.
����� opsdorid�� ���� ���� �޽����� �ְ� ���� �� �ִ�. �׷��� �ϱ� ���ؼ� opsdroid�� �̸��� Ŭ���ϰ� Message opsdroid�� �ش��ϴ� box�� ������ ��������� �ȴ�.

Example of a private message:

```
daniccan [9:06 PM]
hi

opsdroid APP [9:06 PM]
Hi daniccan
```

Connector ��ü�� bot�� �޽����� �Ľ������� �ʴ´�.
