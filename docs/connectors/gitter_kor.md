# Gitter

Gitter�� ���� Connector[Gitter](https://developer.gitter.im/docs/welcome).

Gitter�� �ߺ��� �޽����� ġ�����̴�. Bot�� ���� �޽����� �Ǻ��ϴ� ����� �ߺ��� �޽����� ���� �޽����� �����ؼ� �������ϴ� ���̴�. �̸� ���� �ش��ϴ� ��� �޽����� ���� �� �� �ִ�. �̸� ���ؼ� opsdroid�� ���ſ� �����ߴٰ� ���õǾ �ش��ϴ� �޽����� ���� ���� ���� �� �ִ�. ���� �̸� �ذ��ϴ� ��� �� �ϳ��δ� bot�� ���� ������ �ϳ� �����ؼ� �̸� �ּ� 2�ֵ����� �����ϴ� ���̴�. ���� ������ ���ٸ� �̸� Ǫ�� ����� �����ϰ� gitter ������ ���� ����� �� ���̴�. 
[shadow banning](https://en.wikipedia.org/wiki/Shadow_banning)
[Accounts older than two weeks may be exempt from duplicate detection](https://github.com/opsdroid/opsdroid/issues/1693#issuecomment-754629627)


## Requirements

Gitter Connector�� ����ϱ� ���ؼ� ������� ���� token�� �ʿ��ϴ�. ����ϴ� �� ������ ������ ������ �����ϴ� ���� ��õ�Ѵ�.
### Creating your application

- Bot�� ���� Gitter ����ڸ� �����ϰ� �α����Ѵ�.
- Token�� �����Ѵ�.(https://developer.gitter.im/apps)
- ���ϴ� Room-id�� �Է��Ѵ�.(https://developer.gitter.im/docs/rooms-resource).

## Configuration

```yaml
connectors:
  gitter:
    # Required
    room-id: "to be added"
    token: "to be added"
    # optional
    bot-name: opsdroid # default 'opsdroid'
```
