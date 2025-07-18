# Apex-Specialist-Superbadge
Use integration and business logic to push your Apex coding skills to the limit.


- go to remote site settings and add this - https://th-superbadge-apex.herokuapp.com/equipment ( label anything)

- ### Run the following in Execution Window ( ctrl + E )/(command + E)

String cron = '0 0 1 * * ?'; // 1:00 AM daily
System.schedule('WarehouseSyncScheduleJob', cron, new WarehouseSyncSchedule());
System.enqueueJob(new WarehouseCalloutService());

- Make sure to ### Run all test classes
