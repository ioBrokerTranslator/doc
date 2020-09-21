# Purpose
This repository contains the documentation of the translation process for ioBroker.

General information is found in this file, admins need to look [here](./admin.md) as well.

## Request an adapter to be added to Weblate

If you wish your adapter translations to be managed by Weblate, please ensure the following prerequisites are met and follow the instructions below.

### Prerequisites

The following prerequisites must be met before an adapter can be added to Weblate:

- The adapter must contain the i18n files in a separate folder with the default naming scheme

### Preparation

1. If the adapter is using `gulp`, ensure all files are up-to-date by calling `gulp translateAndUpdateWordsJS` and commit and push those changes to master
1. Configure the following repository hook on GitHub
   - Go to the GitHub page of the adapter
   - Click on the "Settings" tab
   - Click on "Webhooks"
   - Click on "Add webhook"
   - Set the Payload URL to `https://weblate.iobroker.net/hooks/github/` (everything else can be left as-is)
   
### Request

Ask one of the Weblate administrators to add your adapter.

### Review translations

Once an administrator has added your adapter, all translations will be marked as "needing action" (except for English).
Take time to review all translations that you have done manually or that you feel are OK as they are:
1. Go to `https://weblate.iobroker.net/projects/adapters/<your adapter name>/` (e.g. https://weblate.iobroker.net/projects/adapters/tado)
2. Click on a language you translated manually (or that you know well enough to be sure about the translations)
3. Click on "Strings marked for edit"
4. Review the given string and edit it, if needed
5. Uncheck "Needs editing"
6. Click on "Save"
7. Go to step 4. for the next string shown.
8. Once you're done with one language, go to step 1. and choose the next language (if applicable)

### Add badge to README.md

To show that your adapter is being translated with Weblate, please add the following badge after all other badges to your README.md on GitHub:

```markdown
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/<your adapter name>/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)
```
Replace `<your adapter name>` with the name of your adapter (only the part after "ioBroker."). Example:
```markdown
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/tado/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)
```
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/tado/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

## Maintenance of your adapter

### Regularly merge pull requests

Once your adapter is connected to Weblate, you will receive automatic pull requests whenever somebody changes texts in Weblate.
Please make sure, you merge those pull requests as quickly as possible or at least before committing (or merging) code onto your `master` branch.

Reason for this is, you will get merge conflicts locally - or even worse on Weblate - if you don't keep your source code up-to-date. Solving merge conflicts locally is possible and in some cases, it solves conflicts in Weblate, but there are cases where you have no choice but to remove all pending changes in Weblate which leads to lost translations.

### Adding translations

It is still possible to edit language files in your project, but it is strongly recommended to do this only for adding and removing strings; not for editing translations. 
Editing translations locally can cause conflicts with updated translations coming from Weblate.
