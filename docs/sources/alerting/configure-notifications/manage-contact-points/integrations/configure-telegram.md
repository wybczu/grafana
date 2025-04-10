---
canonical: https://grafana.com/docs/grafana/latest/alerting/configure-notifications/manage-contact-points/integrations/configure-telegram/
description: Configure the Telegram integration to connect alerts generated by Grafana Alerting
keywords:
  - grafana
  - alerting
  - telegram
  - integration
labels:
  products:
    - cloud
    - enterprise
    - oss
menuTitle: Telegram
title: Configure Telegram for Alerting
weight: 160
---

# Configure Telegram for Alerting

Use the Grafana Alerting - Telegram integration to send [Telegram](https://telegram.org/) notifications when your alerts are firing.

## Before you begin

### Telegram limitation

Telegram messages are limited to 4096 UTF-8 characters. If you use a `parse_mode` other than `None`, truncation may result in an invalid message, causing the notification to fail.
For longer messages, we recommend using an alternative contact method.

### Telegram bot API token and chat ID

To integrate Grafana with Telegram, you need to get a Telegram **bot API token** and a **chat ID** (the ID of the Telegram chat where you want to receive the alert notifications). To complete the integration, use the browser version of Telegram.

### Set up your Telegram bot

Create a [Telegram bot](https://core.telegram.org/bots/api). You can associate this bot to your chats and perform different actions with it, such as receiving alerts from Grafana.

To set up the bot, complete the following steps.

1. **Open the Telegram app** on your device.
1. Find the Telegram bot named **BotFather**.
1. Type or press `/newbot`.
1. Choose a name for the bot. It must end in **bot** or **\_bot**. E.g. "my_bot".
1. **Copy the API token**.

### Chat ID

Add the bot to a group chat by following the steps below. Once the bot is added to the chat, you will be able to route your alert notifications to that group.

1. In the Telegram app, **open a group or start a new one**.
1. Search and **add the bot to the group**.
1. Copy the **chat ID** from the URL in your browser's address bar. It should look like this: `https://web.telegram.org/a/#-4266674385`.

   The chat ID is the sequence of numbers that follows the `#` symbol. For example: `-4266674385`.

## Procedure

To create your Telegram integration in Grafana Alerting, complete the following steps.

1. Navigate to **Alerts & IRM** -> **Alerting** -> **Contact points**.
1. Click **+ Add contact point**.
1. Enter a contact point name.
1. From the Integration list, select Telegram.
1. In the **BOT API Token** field, copy in the bot API token.
1. In the **Chat ID** field, copy in the chat ID.
1. Click **Test** to check that your integration works.

   ** For Grafana Alertmanager only.**

1. Click **Save contact point**.

## Next steps

The Telegram contact point is ready to receive alert notifications.

To add this contact point to your alert, complete the following steps.

1. In Grafana, navigate to **Alerting** > **Alert rules**.
1. Edit or create a new alert rule.
1. Scroll down to the **Configure labels and notifications** section.
1. Under Notifications click **Select contact point**.
1. From the drop-down menu, select the previously created contact point.
1. **Click Save rule and exit**.
