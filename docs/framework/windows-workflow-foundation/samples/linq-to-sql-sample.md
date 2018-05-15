---
title: LINQ to SQL-Beispiel
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="47f00-102">LINQ to SQL-Beispiel</span><span class="sxs-lookup"><span data-stu-id="47f00-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="47f00-103">Dieses Beispiel veranschaulicht, wie eine Aktivität so erstellt wird, dass LINQ to SQL verwendet wird, um Entitäten aus Tabellen in SQL Server-Datenbanken abzufragen.</span><span class="sxs-lookup"><span data-stu-id="47f00-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47f00-104">Die WCF-Beispiele möglicherweise bereits auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="47f00-104">The WCF samples may already be installed on your machine.</span></span> <span data-ttu-id="47f00-105">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="47f00-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="47f00-106">Wenn dieses Verzeichnis nicht vorhanden ist, klicken Sie auf den Link zum Herunterladen von Beispielen oben auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="47f00-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="47f00-107">Beachten Sie, dass dieser Link heruntergeladen und alle von installiert der [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF und [!INCLUDE[infocard](../../../../includes/infocard-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="47f00-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="47f00-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="47f00-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="47f00-109">Aktivitätsdetails für FindInSqlTable</span><span class="sxs-lookup"><span data-stu-id="47f00-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="47f00-110">Diese Aktivität ermöglicht es Benutzern, Entitäten aus Tabellen in einer Datenbank mit LINQ to SQL abzufragen.</span><span class="sxs-lookup"><span data-stu-id="47f00-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="47f00-111">Benutzer der Aktivität können auch in Form eines Lambda-Ausdrucks ein LINQ-Prädikat bereitstellen, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="47f00-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="47f00-112">Wenn kein Prädikat angegeben wird, wird die ganze Tabelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47f00-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="47f00-113">In der folgenden Tabelle werden die Eigenschaft und die Rückgabewerte für die Aktivität aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="47f00-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="47f00-114">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47f00-114">Property or Return Value</span></span>|<span data-ttu-id="47f00-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47f00-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="47f00-116">`Collection`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="47f00-116">`Collection` property</span></span>|<span data-ttu-id="47f00-117">Eine erforderliche Eigenschaft, die die Quellauflistung angibt.</span><span class="sxs-lookup"><span data-stu-id="47f00-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="47f00-118">`Predicate`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="47f00-118">`Predicate` property</span></span>|<span data-ttu-id="47f00-119">Eine erforderliche Eigenschaft, die den Filter für die Auflistung in Form eines Lambda-Ausdrucks angibt.</span><span class="sxs-lookup"><span data-stu-id="47f00-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="47f00-120">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47f00-120">Return Value</span></span>|<span data-ttu-id="47f00-121">Die gefilterte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="47f00-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="47f00-122">Codebeispiel, in dem die benutzerdefinierte Aktivität verwendet wird</span><span class="sxs-lookup"><span data-stu-id="47f00-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="47f00-123">Im folgenden Codebeispiel wird die benutzerdefinierte `FindInSqlTable`-Aktivität verwendet, um alle Zeilen in einer SQL Server-Tabelle mit dem Namen `Employee` zu finden, bei denen die Spalte `Role` gleich `SDE` ist.</span><span class="sxs-lookup"><span data-stu-id="47f00-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="47f00-124">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="47f00-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="47f00-125">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="47f00-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="47f00-126">Navigieren Sie zum Ordner, der dieses Beispiel enthält.</span><span class="sxs-lookup"><span data-stu-id="47f00-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="47f00-127">Führen Sie die Befehlsdatei "Setup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="47f00-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47f00-128">Das Skript "Setup.cmd" versucht, die Beispieldatenbank in SQL Server Express auf dem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="47f00-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="47f00-129">Wenn Sie es in einer anderen SQL Server-Instanz installieren möchten, bearbeiten Sie "Setup.cmd".</span><span class="sxs-lookup"><span data-stu-id="47f00-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="47f00-130">Das Skript "Setup.cmd" führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="47f00-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="47f00-131">Erstellt eine Datenbank mit dem Namen "LinqToSqlSample".</span><span class="sxs-lookup"><span data-stu-id="47f00-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="47f00-132">Erstellt eine Tabelle "Roles".</span><span class="sxs-lookup"><span data-stu-id="47f00-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="47f00-133">Erstellt eine Tabelle "Employees"</span><span class="sxs-lookup"><span data-stu-id="47f00-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="47f00-134">Fügt 3 Datensätze in die Tabelle "Roles" ein.</span><span class="sxs-lookup"><span data-stu-id="47f00-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="47f00-135">Fügt 12 Datensätze in die Tabelle "Employees" ein.</span><span class="sxs-lookup"><span data-stu-id="47f00-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="47f00-136">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "LinqToSQL.sln".</span><span class="sxs-lookup"><span data-stu-id="47f00-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="47f00-137">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47f00-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="47f00-138">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="47f00-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="47f00-139">So deinstallieren Sie die Beispieldatenbank "LinqToSql"</span><span class="sxs-lookup"><span data-stu-id="47f00-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="47f00-140">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="47f00-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="47f00-141">Navigieren Sie zum Ordner, der dieses Beispiel enthält.</span><span class="sxs-lookup"><span data-stu-id="47f00-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="47f00-142">Führen Sie die Befehlsdatei "Cleanup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="47f00-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47f00-143">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="47f00-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47f00-144">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="47f00-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="47f00-145">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="47f00-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47f00-146">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="47f00-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="47f00-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47f00-147">See Also</span></span>  
 [<span data-ttu-id="47f00-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="47f00-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="47f00-149">Erste Schritte (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="47f00-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
