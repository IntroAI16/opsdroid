# GitHub

Opsdroid�� connector��  [opsdroid](https://github.com/opsdroid/opsdroid) Github�� [GitHub](https://github.com)issues�� pull request�� �����Ѵ�. �� Connector�� �ʿ��� CI check���� ���� �̺�Ʈ�� �����Ѵ�.
## Requirements

Github connector�� ����ϱ� ���ؼ� bot�� ���� ����ڸ��� ���κ� api token�� �����ؾ��Ѵ�. ����� ���� ������ ����ϱ� ���ٴ� ������ ������ ����ϴ� ���� �����Ѵ�. ����� opsdroid�� �̺�Ʈ�� �۽��ϱ� ���ؼ� ������ webhook�� �����ؾ� �Ѵ�. �� ������ ���ؼ� ���ͳ� tunnel�� opsdroid�� ������Ѿ� �Ѵ�.
### Creating your application

There are 2 ways to connect opsdroid to Github. You can create a Github App and point it at opsdroid for event handling. This app can be installed by multiple organizations and would only be configured once. The other way is to use a Webhook within Github and point that to opsdroid for event handling. Each webhook needs to be individually configured.

#### Github Apps method

Opsdroid�� Github�� ���ῡ�� �ΰ��� ����� �ִ�. ù��°�δ� ����� Github���� ����� �̺�Ʈ �ڵ鸵�� ���� �̸� opsdroid�� �������ϴ� ����̴�. Github���� �پ��� ����ȯ�濡���� ��ġ�� �����ϰ� �����ϴ� �͵� ��ȸ������ ����ϴ�. �ι�° ������δ� Webhook�� �̿��ؼ� �̺�Ʈ �ڵ鸵�� ���� opsrdoid�� Github�� �����ϴ� ���̴�. �� webhook�� ���������� �����Ǿ�� �Ѵ�.
Github Apps method
-	Github ���� ��ġ�Ѵ�.
-	Webhook URL�� �����ϰ� �̸� opsdroid url�� �������Ѵ�
-	����ڷκ��� �㰡�� �޴´�. �����ϴ� ������ ������ ����.
	��Checks��
	��Contents��
	��Issues��
	��Pull requests��
-	����� ���ÿ� ���ؼ� Github���� ����� opsdroid�� �۽��ϴ� �̺�Ʈ���� ������ �� �ִ�. �����ϴ� ������ ������ ����.
	��Check runs��
	��Issues��
	��Issue comment��
	��Pull request��
	��Pull request review��
	��Pull request review comment��
	��Push��
-	��Create GitHub App���� Ŭ���ϰ� ���� Ű�� �߱� �޴´�.

#### Webhook method

-	GitHub ����ڸ� ����� �α����Ѵ�.
	���� bot�� GitHub�� �ʹ� ���� �޽����� �����ٸ� ���� ���� �� �ִ�.
-	���� api token�� �����Ѵ�.
-	Bot�� ���������� �ϴ� comment�� repo�� �����Ѵ�.
-	���� ȭ������ �̵��Ѵ�.
-	Webhook â���� ��Add webhook���� ������.
-	���� ��ΰ� application/x-www-form-urlencoded ���� Ȯ���Ѵ�.
-	����� opsdroid url�� ������ �� webhook�� �����Ѵ�.
-	bot���� ���� event�� �����Ѵ�. ����� ���� ������ event�� ���� �� �� �ִ�. �����ϴ� ���� ������ ����.
	��Check runs��
	��Issues��
	��Issue comment��
	��Pull request��
	��Pull request review��
	��Pull request review comment��
	��Push��

## Configuration

#### Github app

```yaml
connectors:
  github:
    # required
    app_id: 123456
    private_key_file: <path/to/private_key.pem>
    secret: <webhook secret>
```

#### Webhook method

```yaml
connectors:
  github:
    # required
    token: aaabbbcccdddeee111222333444
    secret: <webhook secret>
```

## Reference

```eval_rst
.. autoclass:: opsdroid.connector.github.ConnectorGitHub
  :members:
```

## Events Reference

```eval_rst
.. autoclass:: opsdroid.connector.github.events.IssueCreated
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.IssueClosed
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.IssueCommented
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.Push
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PROpened
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReopened
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PREdited
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRMerged
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRClosed
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReviewSubmitted
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReviewEdited
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReviewDismissed
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReviewCommentCreated
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReviewCommentEdited
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.PRReviewCommentDeleted
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.Labeled
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.Unlabeled
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.CheckStarted
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.CheckCompleted
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.CheckPassed
  :members:
```

```eval_rst
.. autoclass:: opsdroid.connector.github.events.CheckFailed
  :members:
```