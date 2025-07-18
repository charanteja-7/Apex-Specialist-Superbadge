# Apex Specialist Superbadge

This repository contains code for the Salesforce Apex Specialist Superbadge.

-----

## Setup

Before you begin, set up your Salesforce Org as follows:

  * **Create a new Trailhead Playground or Developer Edition Org** for this superbadge. Using this org for any other reason might create problems when validating the challenge.
  * **Install this unlocked package** (package ID: `04t6g000008av9iAAA`). This package contains metadata you'll use to complete this challenge. If you have trouble installing this package, follow the steps in the Install a Package or App to Complete a Trailhead Challenge help article.
  * **Add picklist values** `Repair` and `Routine Maintenance` to the **Type** field on the **Case** object.
  * **Update the Case page layout assignment** to use the **Case (HowWeRoll) Layout** for your profile.
  * **Rename the tab/label** for the **Case** tab to **Maintenance Request**.
  * **Update the Product page layout assignment** to use the **Product (HowWeRoll) Layout** for your profile.
  * **Rename the tab/label** for the **Product** object to **Equipment**.
  * **Use App Launcher to navigate to the Create Default Data tab** of the **How We Roll Maintenance** app. Click **Create Data** to generate sample data for the application.
  * **Review the newly created records** to get acquainted with the data model.

-----

## Execution

### 1\. Remote Site Setting

Add the following to **Remote Site Settings**:

  * **URL:** `https://th-superbadge-apex.herokuapp.com/equipment`
  * **Label:** (Any label, e.g., `EquipmentService`)

-----

### 2\. Run in Execution Window

Open the Developer Console, then the Execution Window (`Ctrl + E` / `Command + E`), and run:

```apex
String cron = '0 0 1 * * ?'; // 1:00 AM daily
System.schedule('WarehouseSyncScheduleJob', cron, new WarehouseSyncSchedule());
System.enqueueJob(new WarehouseCalloutService());
```

-----

### 3\. Run All Test Classes

Ensure all Apex test classes pass for full code coverage.

-----
