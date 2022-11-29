| [Home](../README.md) |
|--------------------------------------------|

# Installation

1. To install a solution pack, click **Content Hub** > **Discover**.
2. From the list of solution pack that appears, search for and select **SLA Notification**.
3. Click the **SLA Notification** solution pack card.
4. Click **Install** on the bottom to begin installation.

## Prerequisites
**Not Applicable**

## Configuration:
- Configuration step **@Incidents SLA Notification:** playbook
    -  email_recipient: If you want to send all notifications to the same recipient. Leave empty for the notifications to be sent to the record owner
    -  create_announcement: if set to: **True** an announcement record will be created for each notification which can be used as a trigger for FortiSOAR system notifications (**Settings > Notifications**)
    -  channel_name: name of the MS-Teams channel where you want the notification to be sent

- Configuration step **@Alerts SLA Notifier:** playbook
    -  email_recipient: If you want to send all notifications to the same recipient. Leave empty for the notifications to be sent to the record owner
    -  create_announcement: if set to: **True** an announcement record will be created for each notification which can be used as a trigger for FortiSOAR system notifications (**Settings > Notifications**)
    -  channel_name: name of the MS-Teams channel where you want the notification to be sent

- Connectors:
    - MS Exchange
    - MS Teams (for Teams notifications, remove the step from playbooks if not required)

- Schedule:
    - Schedule the playbooks below to run each 10 minutes or so (depending on your SLA policy you can increase or decrease the checks frequencies):
        - Alerts SLA Notification
        - Incidents SLA Notification
