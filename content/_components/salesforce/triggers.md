---
title: Salesforce triggers
layout: component
description: Salesforce component triggers.
icon: salesforce.png
icontext: Salesforce component
category: salesforce
createdDate: 2020-03-17
updatedDate: 2020-03-17
---

## Query trigger

Continuously runs the same SOQL Query and emits results one-by-one.
Use the Salesforce Object Query Language (SOQL) to search your organization’s Salesforce data for specific information. SOQL is similar to the SELECT statement in the widely used Structured Query Language (SQL) but is designed specifically for Salesforce data. This action allows you to interact with your data using SOQL.

### List of Expected Config fields trigger

* **SOQL Query** - Input field for your SOQL Query

* **Output method** - dropdown list with options: `Emit all` - all found records will be emitted in one array `records`, and `Emit individually` - each found object will be emitted individual. Optional field, defaults to: `Emit individually`.


## Get New and Updated Objects Polling trigger

Polls existing and updated objects. You can select any custom or built-in object for your Salesforce instance.

### Input field description

* **Object** - Input field where you should select the type of object which updates you want to get. E.g. `Account`;

* **Start Time** - Indicates the beginning time to start polling from. Defaults to `1970-01-01T00:00:00.000Z`;

* **End Time** - If provided, don’t fetch records modified after this time;

* **Size of Polling Page** - Indicates the size of pages to be fetched. You can set positive integer, max `10 000`, defaults to `1000`;

* **Process single page per execution** - You can select on of options (defaults to `yes`):

   1. `yes` - if the number of changed records exceeds the maximum number of results in a page, wait until the next flow start to fetch the next page;

   2. `no` - if the number of changed records exceeds the maximum number of results in a page, the next pages will fetching in the same execution.

* **Output method** - dropdown list with options: `Emit all` - all found records will be emitted in one array `records`, and `Emit individually` - each found object will be emitted individual. Optional field, defaults to: `Emit individually`.

For example, you have 234 “Contact” objects, 213 of them were changed from 2019-01-01.
You want to select all “Contacts” that were changed from 2019-01-01, set the page size to 100 and process single page per execution.

For you purpose you need to specify following fields:

   * Object: `Contact`

   * Start Time: `2019-01-01T00:00:00.000Z`

   * Size of Polling Page: `100`

   * Process single page per execution: `yes` (or leave this empty)

![Get New and Updated Objects Polling - configure input](img/configure-input.png)

As a result, all contacts will be fetched in three calls of the trigger: two of them by 100 items, and the last one by 13.
If you select `no` in **Process single page per execution**, all 213 contacts will be fetched in one call of the trigger.

## Subscribe to platform events trigger

>**NOTE:** REALTIME FLOWS ONLY

This trigger will subscribe for any platform Event using Salesforce streaming API.

### Input field description

* **Event object name** - Input field where you should select the type of platform event which you want to subscribe E.g. `My platform event`

### How to create new custom Platform event Entity:

`Setup --> Integrations --> Platform Events --> New Platform Event`

![Platform Events](img/platform-events.png)

You can find more detail information in the [Platform Events Intro Documentation](https://developer.salesforce.com/docs/atlas.en-us.platform_events.meta/platform_events/platform_events_intro.htm).

### Environment Variables

1. `SALESFORCE_API_VERSION` - API version for not deprecated actions and triggers e.g(46.0), default value 45.0

2. `LOG_LEVEL` - `trace` | `debug` | `info` | `warning` | `error` controls logger level

### Limitations:

At the moment this trigger can be used only for **"Realtime"** flows.

## New Case trigger(deprecated)

Polls existing and updated Cases (fetches a maximum of 1000 objects per execution)

Trigger is `deprecated`. You can use [Get New and Updated Objects Polling](#get-new-and-updated-objects-polling-trigger) trigger instead.

## New Lead trigger(deprecated)

Polls existing and updated Leads (fetches a maximum of 1000 objects per execution)

Trigger is `deprecated`. You can use [Get New and Updated Objects Polling](#get-new-and-updated-objects-polling-trigger) trigger instead.

## New Contact trigger(deprecated)

Polls existing and updated Contacts (fetches a maximum of 1000 objects per execution)

Trigger is `deprecated`. You can use [Get New and Updated Objects Polling](#get-new-and-updated-objects-polling-trigger) trigger instead.

## New Account trigger(deprecated)

Polls existing and updated Accounts (fetches a maximum of 1000 objects per execution)

Trigger is `deprecated`. You can use [Get New and Updated Objects Polling](#get-new-and-updated-objects-polling-trigger) trigger instead.

## New Task trigger(deprecated)

Polls existing and updated Tasks (fetches a maximum of 1000 objects per execution)

Trigger is `deprecated`. You can use [Get New and Updated Objects Polling](#get-new-and-updated-objects-polling-trigger) trigger instead.
