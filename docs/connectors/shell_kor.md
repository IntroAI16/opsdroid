# Shell

Command line�� ���� opsdroid�� �޽��� �۽��ϴ� connector [opsdroid](https://github.com/opsdroid/opsdroid).

�� connector�� unixȯ�濡���� �۵��� �Ѵ�. �����쿡���� �۵��� ���� �ʴ´�. �����쿡�� Ȱ���Ϸ��� Opsdroid ��ǻ�� ������ �ٿ�ε� �ؾ��Ѵ�.
[Opsdroid Desktop App](https://github.com/opsdroid/opsdroid-desktop).

## Requirements

Shell connector�� ������� ������ �ʿ�� �Ѵ�.

## Configuration

```yaml
connectors:
  shell:
    # optional
    bot-name: "mybot" # default "opsdroid"
```

## Disable Logging

console �α����� ��Ȱ��ȭ�ϴ� ���� ��õ�Ѵ�. Configuration.yaml�� �̿��ؼ� connector�� �߰��ϸ� �ȴ�. ���� ���� configuration ���Ͽ� �߰��ϸ� �ȴ�.


```yaml
logging:
  console: false
```
