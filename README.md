# SQL-Job
Originally published on  [Microsoft Technet](https://gallery.technet.microsoft.com/scriptcenter/Create-SQL-Job-for-Azure-16ba16ec) with close to 1,000 downloads

## Description

This runbook is designed to replicate the "SQL Server Agent job" functionality of a SQL Server in Azure SQL. A SQL job is used to run database management tasks or other value-added database tasks on a SQL Server database. The result, either success or failure, of the execution of this job is logged in Application Insights for future audits. It is recommended that the SQL query executes a pre-programmed database stored procedure for better security and audit.

## Requirements

For this runbook to work, the SQL Server must be accessible from the runbook worker running this runbook. Make sure the SQL Server allows incoming connections from Azure services by selecting 'Allow Windows Azure Services' on the SQL Server configuration page in Azure. This runbook also requires an Automation Credential asset be created before the runbook is run, which stores the username and password of an account with access to the SQL Server. That credential should be referenced for the SqlCredential parameter of this runbook.

Finally, to log to Applications Insights, the Custom Events Module ("ApplicationInsightsCustomEvents.zip") must be imported in the Automation account under the "Modules" pane. The zip file can be found [here](https://gallery.technet.microsoft.com/scriptcenter/Log-Custom-Events-into-847900d7)
