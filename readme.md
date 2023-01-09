# Slack Unprivatomator

This script takes as input a zip archive containing the exported json data of a single private Slack channel and outputs another zip archive containing modified json. The modifications allow for the Slack channel to be changed from private to public whilst maintaining all external file links (which are normally destroyed in this process).

### Requirements

You will need the ability to export the private slack channel(s) that you want to convert to public. I have not tried all of these but I believe this can be achieved by 3 different methods. Please let me know if you can confirm or deny any of them.

1) By being invited to the private channel and having a license for Backupery for Slack available here: `https://www.backupery.com/`

2) Having an Enterprise Cloud Slack license (very expensive) and downloading the data from here: `https://<subdomain>.slack.com/services/export`

3) Contacting Slack directly and asking if they can give you temporary permissions to export private channels. This might require a serious reason such as a Data Subject Access Request.

We are going to cover using Backupery.

### How to use this script

Navigate to `https://<subdomain>.slack.com/services/export` replacing `<subdomain>`
appropriately for your situation.

<p align="center">
     <img src="https://github.com/eM7RON/Slack-Unprivatomator/blob/master/img/slack-export.png" alt="Slack Export" width="900"/>
</p>

TLDR: exports via Backupery won't have the access token required for external links. We need to get an access token by downloading any data from the official Slack export page. The full explanation is here: `https://www.backupery.com/slack-import-tool-doesnt-import-files-from-a-zip-archive-produced-by-backupery-for-slack/`.

<p align="center">
     <img src="https://github.com/eM7RON/Slack-Unprivatomator/blob/master/img/slack-export-download.png" alt="Slack Export" width="900"/>
</p>

Download the export and extract the zip archive. Inside there should be a directory with the same name as a channel you exported. Inside should be a load of json files named after dates. Open one of these files and locate the access token which is part of a url named "url_private_download"

<p align="center">
     <img src="https://github.com/eM7RON/Slack-Unprivatomator/blob/master/img/token-location.png" alt="Slack Export" width="900"/>
</p>

