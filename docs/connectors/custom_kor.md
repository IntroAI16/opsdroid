## Creating a custom connector

Connectors�� opsdroid Connector�� Ȯ������ִ� class�̴�. Connect, listen, respond �� ������ method�� �����Ѵ�. �⺻ �������� __init__�Լ��� ���� ����� �� �ִ�. �ش� �Լ��� �����ϴ� �⺻ �������� ��� �����Ǿ� �ִ��� Ȯ���ؾ��Ѵ�.
#### configuration  (property)
Configuration �� Connector class�� �Ӽ��̴�. Connector�� ���� ������ �����ϴµ� ���ȴ�. Configuration.yaml���� Connector�� Ư�� �Ű������� �˻��� �� �ִ�.
#### connect
Connect�� Ư���� ��ȭ ���񽺿� �����ϴ� method�̴�.

### Methods

#### listen
�� �޽������� ��� opsdriod Message object �������� ��ȯ�ǰ� �Ľ̵ȴ�. ���ѷ����� �����԰� ���ÿ� ���� �޽����� ��ٷ� opsdroid�� �Բ� �Ľ��ؾ� �ϱ� ������ await�Լ��� ����Ѵ�. Event loop�� ��������μ� �ٸ� �޽����� ��ٸ��� ���� �ٸ� �Լ����� ����� �� �ְԲ� �Ѵ�.
#### user_typing
User_typing�� connector�� ����� ��� ��user is typing�� �̺�Ʈ �޽����� ����Ѵ�. �̰��� �̿��ؼ� trigger ������ ���� �̺�Ʈ on/off�� boolean������ �����Ѵ�.
#### disconnect
Disconnect ���� upon shutdown�̶�� disconnect �Լ��� �����Ѵ�. Connector�� disconnect�� ��Ÿ����.

### Handling Events

Opsdroid�� ���� ������ ��/���� �̺�Ʈ�� �����Ѵ�. Events documentation ������ ���ؼ� ���� ������ ������ �ľ��� �� �ִ�.

Connectors�� �������� �۽� �̺�Ʈ���� opsdroid.connector.register_event decorator�� ���� implements�� �� �ִ�. �� decorator�� ���� �ٸ� ������ connector support�� method�� �����ϴµ� ���ȴ�.

```python

@register_event(Message)
async def send(self, message):
    await myservice.send(message.text)

```

�� �׸��� Connector.send�� Message object�� �Բ� �ҷ����� method�̴�. �̷��� ������ method�� Connector�� �����ϴ� ��� �̺�Ʈ�� ������ �� �ִ�.
```python

import time

# We recommend you use the official library
# for your chat service and import it here
import chatlibrary

# Import opsdroid dependencies
from opsdroid.connector import Connector, register_event
from opsdroid.events import Message


class MyConnector(Connector):

  def __init__(self, config, opsdroid):
    # Init the config for the connector
    self.name = "MyConnector" # The name of your connector
    self.config = config # The config dictionary to be accessed later
    self.default_target = "MyDefaultRoom" # The default room for messages to go
    self.opsdroid = opsdroid # An instance of opsdroid.core.

  async def connect(self, opsdroid):
    # Create connection object with chat library
    self.connection = await chatlibrary.connect()

  async def listen(self):
    # Listen for new messages from the chat service
    while True:
      # Get raw message from chat
      raw_message = await self.connection.get_next_message()

      # Convert to opsdroid Message object
      #
      # Message objects take a pointer to the connector to
      # allow the skills to call the respond method
      message = Message(raw_message.text, raw_message.user,
                        raw_message.room, self)

      # Parse the message with opsdroid
      await opsdroid.parse(message)

  @register_event(Message)
  async def send(self, message):
    # Send message.text back to the chat service
    await self.connection.send(message.text, message.user,
                               message.target)

  async def disconnect(self):
    # Disconnect from the chat service
    await self.connection.disconnect()

```

---
You might also be interested in reading the [configuration reference - Connector Modules](../configuration.html#connector-modules) in the documentation.
*If you need help or if you are unsure about something join our* [matrix channel](https://app.element.io/#/room/#opsdroid-general:matrix.org) *and ask away! We are more than happy to help you.*
