# Overview

**Cronicle** is a multi-server task scheduler and runner, with a web based front-end UI.  It handles both scheduled, repeating and on-demand jobs, targeting any number of worker servers, with real-time stats and live log viewer.  It's basically a fancy [Cron](https://en.wikipedia.org/wiki/Cron) replacement written in [Node.js](https://nodejs.org/).  You can give it simple shell commands, or write Plugins in virtually any language.

![Main Screenshot](https://pixlcore.com/software/cronicle/screenshots-new/job-details-complete.png)

## Features at a Glance

* Single or multi-server setup.
* Automated failover to backup servers.
* Auto-discovery of nearby servers.
* Real-time job status with live log viewer.
* Plugins can be written in any language.
* Schedule events in multiple timezones.
* Optionally queue up long-running events.
* Track CPU and memory usage for each job.
* Historical stats with performance graphs.
* Simple JSON messaging system for Plugins.
* Web hooks for external notification systems.
* Simple REST API for scheduling and running events.
* API Keys for authenticating remote apps.

## Documentation

The Cronicle documentation is split up across these files:

- &rarr; **[Installation & Setup](https://github.com/jhuckaby/Cronicle/blob/master/docs/Setup.md)**
- &rarr; **[Configuration](https://github.com/jhuckaby/Cronicle/blob/master/docs/Configuration.md)**
- &rarr; **[Web UI](https://github.com/jhuckaby/Cronicle/blob/master/docs/WebUI.md)**
- &rarr; **[Plugins](https://github.com/jhuckaby/Cronicle/blob/master/docs/Plugins.md)**
- &rarr; **[Command Line](https://github.com/jhuckaby/Cronicle/blob/master/docs/CommandLine.md)**
- &rarr; **[Inner Workings](https://github.com/jhuckaby/Cronicle/blob/master/docs/InnerWorkings.md)**
- &rarr; **[API Reference](https://github.com/jhuckaby/Cronicle/blob/master/docs/APIReference.md)**
- &rarr; **[Development](https://github.com/jhuckaby/Cronicle/blob/master/docs/Development.md)**

## Glossary

A quick introduction to some common terms used in Cronicle:

| Term | Description |
|------|-------------|
| **Primary Server** | The primary server which keeps time and runs the scheduler, assigning jobs to other servers, and/or itself. |
| **Backup Server** | A worker server which will automatically become primary and take over duties if the current primary dies. |
| **Worker Server** | A server which sits idle until it is assigned jobs by the primary server. |
| **Server Group** | A named group of servers which can be targeted by events, and tagged as "primary eligible", or "worker only". |
| **API Key** | A special key that can be used by external apps to send API requests into Cronicle.  Remotely trigger jobs, etc. |
| **User** | A human user account, which has a username and a password.  Passwords are salted and hashed with [bcrypt](https://en.wikipedia.org/wiki/Bcrypt). |
| **Plugin** | Any executable script in any language, which runs a job and reads/writes JSON to communicate with Cronicle. |
| **Schedule** | The list of events, which are scheduled to run at particular times, on particular servers. |
| **Category** | Events can be assigned to categories which define defaults and optionally a color highlight in the UI. |
| **Event** | An entry in the schedule, which may run once or many times at any interval.  Each event points to a Plugin, and a server or group to run it. |
| **Job** | A running instance of an event.  If an event is set to run hourly, then a new job will be created every hour. |

