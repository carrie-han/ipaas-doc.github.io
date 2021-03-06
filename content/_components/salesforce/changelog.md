---
title: Changelog
layout: component
description: Changelog for Salesforce Component.
icon: salesforce.png
icontext: Salesforce component
category: salesforce
createdDate: 2020-01-02
updatedDate: 2020-03-11
---

## 1.3.1 (March 11, 2020)

* Add new optional field `Output method` in triggers: `Query` and `Get New and Updated Objects Polling`

## 1.3.0 (February 27, 2020)

* Add Delete Object (at most 1) Action
* Add new optional field in the Lookup Object Action

## 1.2.3 (February 4, 2020)

* Fix query action

## 1.2.2 (January 25, 2020)

* Add request caching for lookup actions

## 1.2.1 (December 27, 2019)

* Update sailor version to 2.5.4
* Refactor console.log to built in sailor logger
* Change build type to `docker`


## 1.2.0 (December 2, 2019)

* Add support for `Bulk operations` feature (Create/Update/Delete and Query)
* Add `Delete Object` action
* Add `Lookup Objects` action
* `Create object` action: add ability to utilize binary data attachment from previous step
* `Upsert object` action: add ability to utilize binary data attachment from previous step
* `Lookup Object (at most 1)` action: add ability to pass binary data (if found object has it) to the next component as a binary attachment
* `Query` action: add ability to query deleted objects

## 1.1.2 (October 28, 2019)

* Change Oauth values naming

## 1.1.1 (July 10, 2019)

* Add support for `Create Attachment` feature
* Fix bug with Salesforce's and platform's types mismatch
* Make unit tests great again (internal issue)

## 1.0.0 (June 27, 2019)

* Initial release which includes a bunch of previous unversioned releases
