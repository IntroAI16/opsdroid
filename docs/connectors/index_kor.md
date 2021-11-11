# Connectors

Connectors�� opsdroid�� �ܺ� �̺�Ʈ �ڷ�� ���� ���ִ� ���̴�. �̰��� Slack�̳� Matrixó�� ä�� ���� �ϼ� �ְ� webhook endpoint�� ���� �̺�Ʈ�ϼ��� �ִ�. 

```eval_rst
.. toctree::
   :maxdepth: 1

   facebook
   github
   gitter
   mattermost
   matrix
   rocketchat
   shell
   slack
   teams
   telegram
   twitch
   webexteams
   websocket
   custom
```

## Using two of the same connector type

�ʰ� �ʿ��ϴٸ� �ʴ� �ΰ��� connector�� ��� �� �� �ִ�. ���� ��� �ʰ� Slack connectors�� ���Ѵٸ� 

```yaml
connectors:
  slack:
      bot-token: "xoxb-abdcefghi-12345"
  slack-two:
      bot-token: "xoxb-12345-abdcefghi"
      module: opsdroid.connector.slack
```

�Ʒ��� ���� �ΰ����� �о�� �� �ִ�. �� �� �ϳ����� �о���� �͵� �����ϴ�.

```python
# Use 'slack-two' connector
slack_two = opsdroid.get_connector("slack-two")
```