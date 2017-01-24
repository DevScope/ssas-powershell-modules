# ssas-powershell-modules
A single lightweight powershell module with cmdlets to manage SSAS Instances (On-Prem or Azure)
Complete samples provided with the modules!

##(Re)Create Partitions

```powershell

Invoke-SSASCreatePartition `
    -connectionString $connStr `
    -database "AW Internet Sales Tabular Model" `
    -table "Internet Sales" -partition "Internet Sales 2014" `
    -datasource "Adventure Works DB from SQL" `
    -query $query `
    -verbose

```

##Process Partition

```powershell

Invoke-SSASProcessCommand -connectionString $connStr -database "AW Internet Sales Tabular Model" -table "Internet Sales" -partition "Internet Sales 2014" -Verbose

```

##Process Table

```powershell

Invoke-SSASProcessCommand -connectionString $connStr -database "AW Internet Sales Tabular Model" -table "Internet Sales" -Verbose

```

##Process Database

```powershell

Invoke-SSASProcessCommand -connectionString $connStr -database "AW Internet Sales Tabular Model" -Verbose

```

##Suspend/Resume Azure AS

```powershell

Set-AzureASState `
    -resourceGroupName "YourResourceGroup" `
    -serverName "YourServerName" `
	-ApplicationID "YourApplicationId" `
	-ApplicationKey "YourApplicationKey" `
	-tennantid "YourTennantId" `
	-SubscriptionId "YourSubsciptionId" `
	-action "suspend"

```
# Full tuto on https://devscopebi.wordpress.com/2016/12/14/automate-azure-analysis-services-pauseresume-using-powershell/

## Authors

* **Rui Romano** - *Initial work & Supervisor* - https://ruiromanoblog.wordpress.com/
* **Filipe Sousa** - www.linkedin.com/in/filipe-sousa-939b8b65

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Thanks to Josh Caplan - https://www.linkedin.com/in/josh-caplan-2139a3a6 - who pointed us the way to Azure AS automation in a time where no one had a clue about how to do it!