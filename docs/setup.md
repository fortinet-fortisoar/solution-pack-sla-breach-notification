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

- Connectors:
    - MS Exchange
    - MS Teams (for Teams notifications, remove the step from playbooks if not required)

- Schedule:
    - Schedule the playbooks below to run each 10 minutes or so (depending on your SLA policy you can increase or decrease the checks frequencies):
        - Alerts SLA Notification
        - Incidents SLA Notification

## Content:
- Playbooks:
    - Create Alerts and Incidents Records
    - Alerts SLA Notification
    - Incidents SLA Notification
    - Send Message to Teams Channel
- Dashboard:
   - SLA Monitor

- Configuration step **@Send Message to Teams Channel** playbook
    -  notification_teams_id: ID of the Teams where the channel you want to send the notification to is located (you can get it from the team URL: In MS-Teams: Select the team > more options > Get the link to team)

## Usage:

Run the playbook: **Create Alerts and Incidents Records** to populate FortiSOAR with sample records, then browse to **SLA Notification** Dashboard
