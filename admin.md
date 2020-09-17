# Admin Guide

This guide explains the different tasks ioBroker Weblate administrators need to perform.

## Add a new adapter

### Prerequisites

The following prerequisites must be met before an adapter can be added to Weblate:

- The adapter must contain the i18n files in a separate folder with the default naming scheme
- If the adapter is using `gulp`, ensure all files are up-to-date by calling `gulp translateAndUpdateWordsJS` and commit and push those changes

### Create component in Weblate

1. Navigate to https://weblate.iobroker.net/projects/adapters/ and click on "Add new translation component"
1. Provide the following input:
   - Component name: Name of the adapter in lowercase without "ioBroker." (Example: `loxone` for the adapter ioBroker.loxone)
   - URL slug: same as component name above - do not shorten it!
   - Project: leave at `ioBroker Adapters`
   - Version control system: change to `GitHub`
   - Source repository: HTTPS URL of the repository (Example: `https://github.com/UncleSamSwiss/ioBroker.loxone`)
   - Repository branch: always `master`
1. Start the detection by clicking on "Continue"
1. Choose translation files to import:
   - File format is always `JSON file`
   - Filemask is similar to `admin/i18n/*/translations.json`
1. Click on "Continue"
1. Review the settings and update the following (everything else should be ok as it is):
   - Repository browser: `https://github.com/<user>/<name>/blob/{{branch}}/{{filename}}#L{{line}}` (Example: `https://github.com/ioBroker/ioBroker.zigbee/blob/{{branch}}/{{filename}}#L{{line}}`)
   - Translation license: should be equal to the license of the adapter (usually found in LICENSE file of the given adapter)
1. Click on "Save" to create the component
1. Once the creation is completed, click on "Return to the component"
1. Go to "Manage" > "Addons"
1. Install the following addons one by one:
   - `Flag unchanged translations as "Needs editing"`
   - `Flag new source strings as "Needs editing"`
   - `Flag new translations as "Needs editing"`
   - If the adapter uses Gulp to generate the words.js, also install `ioBroker: Save translations into words.js`
1. Go back to the component and choose "Manage" > "Settings"
   - Go to the tab "Version control"
   - Scroll to the bottom and change "Age of changes to commit" to `3`
   - Click on "Save" to store this change
1. Go back to the component and choose "Tools" > "Bulk edit"
   - Make a custom search for `NOT language:en`
   - Set state to `Needs editing`
   - Press "Apply"
   - This will mark all texts as needing action (except for the base language English)
