# Mautic Housekeeping Bundle
This bundle provides a Mautic Houseekping Command for database cleanup purposes.

## Command

Command to delete Lead_Event_Log, Campaign_Lead_Event_Log & Email_stats table entries. 

```
bin/console mautic:leuchtfeuer:housekeeping
```
By default, entries older than 365 days are deleted from the CampaignLeadEventLog, LeadEventLog & EmailStats tables.
### Parameter
```
-d  | --days-old      | Specifies the minimum age of the entries to be deleted. Default: 365 days
-r  | --dry-run       | Execute as dry run. No entries will be deleted
-i  | --cmp-id        | Delete only data for a specific campaign ID from campaign_lead_event_log
-c  | --campaign-lead | Only entries from the campaign_lead_event_log table will be deleted
-m  | --email-stats   | Only entries from the email_stats table will be deleted.
-l  | --lead          | Only entries from the lead_event_log table will be deleted.
```


### Installation
- Plugin must be saved under plugins/MauticHouskeepingBundle/ 

- Afterwards, the cache must be cleared.


## Notice
- Every last entry from the campaign_lead_event_log per campaign will be kept. This is due to contacts restarting campaigns if there is no last step preserved in the log. 
