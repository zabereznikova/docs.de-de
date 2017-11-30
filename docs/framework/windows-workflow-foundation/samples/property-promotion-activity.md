---
title: "Aktivität zur Höherstufung einer Eigenschaft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd8356927ad7cb4c24cc278fcb901cc543c6d7b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="property-promotion-activity"></a><span data-ttu-id="5bcbb-102">Aktivität zur Höherstufung einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5bcbb-102">Property Promotion Activity</span></span>
<span data-ttu-id="5bcbb-103">In diesem Beispiel wird eine End-to-End-Projektmappe bereitgestellt, mit der die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Funktion zur Höherstufung direkt in die Workflowerstellung integriert wird.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-103">This sample provides an end-to-end solution that integrates the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature directly into the workflow authoring experience.</span></span> <span data-ttu-id="5bcbb-104">Eine Auflistung von Konfigurationselementen, Workflowaktivitäten und Workflowerweiterungen wird bereitgestellt, um die Verwendung der Funktion zur Höherstufung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-104">A collection of configuration elements, workflow activities, and workflow extensions that simplify the use of the Promotion feature are provided.</span></span> <span data-ttu-id="5bcbb-105">Außerdem enthält das Beispiel einen einfachen Workflow, mit dem die Verwendung dieser Auflistung veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-105">Additionally, the sample contains a simple workflow that demonstrates how to use this collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bcbb-106">Die Beispiele dienen nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-106">Samples are provided for educational purposes only.</span></span> <span data-ttu-id="5bcbb-107">Sie sollten nicht in einer Produktionsumgebung eingesetzt werden und wurden vorher nicht in einer Produktionsumgebung getestet.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-107">They are not intended for a production environment, and have not been tested in a production environment.</span></span> <span data-ttu-id="5bcbb-108">Microsoft bietet keinen technischen Support für diese Beispiele.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-108">Microsoft does not provide technical support for these samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5bcbb-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5bcbb-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="5bcbb-110"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Datenbank (initialisiert)</span><span class="sxs-lookup"><span data-stu-id="5bcbb-110">An initialized <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a><span data-ttu-id="5bcbb-111">Beispielprojekte</span><span class="sxs-lookup"><span data-stu-id="5bcbb-111">Sample Projects</span></span>  
  
-   <span data-ttu-id="5bcbb-112">Die **PropertyPromotionActivity** Projekt enthält Dateien mit der Promotion-spezifischen Konfigurationselementen, Workflowaktivitäten und workflowerweiterungen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-112">The **PropertyPromotionActivity** project contains files pertaining to the promotion-specific configuration elements, workflow activities, and workflow extensions.</span></span>  
  
-   <span data-ttu-id="5bcbb-113">Die **CounterServiceApplication** Projekt enthält einen Beispielworkflow, die mithilfe der **SqlWorkflowInstanceStorePromotion** Projekt.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-113">The **CounterServiceApplication** project contains a sample workflow that uses the **SqlWorkflowInstanceStorePromotion** project.</span></span>  
  
-   <span data-ttu-id="5bcbb-114">Ein SQL-Skript (PropertyPromotionActivitySQLSample.sql), das für die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Datenbank ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-114">A SQL script (PropertyPromotionActivitySQLSample.sql) that must be run against the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database.</span></span>  
  
-   <span data-ttu-id="5bcbb-115">Eine Projektmappendatei, mit der die beiden [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Projekte verknüpft werden (`PropertyPromotionActivity.sln`).</span><span class="sxs-lookup"><span data-stu-id="5bcbb-115">A solution file that links the two [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] projects (`PropertyPromotionActivity.sln`)</span></span>  
  
## <a name="to-set-up-and-run-the-sample"></a><span data-ttu-id="5bcbb-116">So richten Sie das Beispiel ein und führen es aus</span><span class="sxs-lookup"><span data-stu-id="5bcbb-116">To set up and run the sample</span></span>  
  
1.  <span data-ttu-id="5bcbb-117">Initialisieren Sie eine Workflowpersistenzdatenbank.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-117">Initialize a workflow persistence database.</span></span>  
  
    1.  <span data-ttu-id="5bcbb-118">Navigieren Sie zum Beispielverzeichnis (\WF\Basic\Persistence\PropertyPromotionActivity), und führen Sie CreateInstanceStore.cmd aus.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-118">Navigate to the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity) and run CreateInstanceStore.cmd.</span></span>  
  
    2.  <span data-ttu-id="5bcbb-119">Wenn Sie nicht über Administratorberechtigungen verfügen, erstellen Sie eine SQL Server-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-119">If Administrator privileges are not available, create a SQL Server login.</span></span> <span data-ttu-id="5bcbb-120">Wechseln Sie in SQL Server Management Studio zu **Sicherheit**, **Anmeldungen**.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-120">In SQL Server Management Studio, go to **Security**, **Logins**.</span></span> <span data-ttu-id="5bcbb-121">Mit der rechten Maustaste **Anmeldungen** und eine neue Anmeldung erstellen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-121">Right-click **Logins** and create a new login.</span></span> <span data-ttu-id="5bcbb-122">Der SQL-Rolle Ihr ACL-Benutzerkonto hinzufügen, durch Öffnen des **Datenbanken**, **InstanceStore**, **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-122">Add your ACL user to the SQL role by opening **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="5bcbb-123">Mit der rechten Maustaste **Benutzer** , und wählen Sie **neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-123">Right-click **Users** and select **New user**.</span></span> <span data-ttu-id="5bcbb-124">Legen Sie die **Anmeldename** auf den vorherigen Schritt erstellten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-124">Set the **Login name** to the user created above.</span></span> <span data-ttu-id="5bcbb-125">Fügen Sie den Benutzer der Datenbankrollenmitgliedschaft System.Activities.DurableInstancing.InstanceStoreUsers (und anderen) hinzu.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-125">Add the user to the Database role membership System.Activities.DurableInstancing.InstanceStoreUsers (and others).</span></span> <span data-ttu-id="5bcbb-126">Beachten Sie, dass der Benutzer möglicherweise bereits vorhanden ist (z. B. als DBO).</span><span class="sxs-lookup"><span data-stu-id="5bcbb-126">Note that the user might exist already (for example, user dbo).</span></span>  
  
2.  <span data-ttu-id="5bcbb-127">Öffnen Sie die Projektmappendatei PropertyPromotionActivity.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bcbb-127">Open the PropertyPromotionActivity.sln solution file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="5bcbb-128">Wenn Sie den Instanzspeicher nicht in der lokalen Installation von SQL Server Express, sondern in einer anderen Datenbank erstellt haben, müssen Sie die Datenbankverbindungszeichenfolge aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-128">If you created the instance store in a database other than a local installation of SQL Server Express, then you must update the database connection string.</span></span> <span data-ttu-id="5bcbb-129">Ändern Sie die Datei "App.config" unter der **CounterServiceApplication** durch Festlegen des Werts von der `connectionString` -Attribut auf die `sqlWorkflowInstanceStorePromotion` Knoten, damit er in die Persistenzdatenbank zeigt, der initialisiert wurde in Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-129">Alter the App.config file under the **CounterServiceApplication** by setting the value of the `connectionString` attribute on the `sqlWorkflowInstanceStorePromotion` node so that it points to the persistence database that was initialized in step 1.</span></span>  
  
4.  <span data-ttu-id="5bcbb-130">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-130">Build and run the solution.</span></span> <span data-ttu-id="5bcbb-131">Dadurch wird der WF-Zählerdienst gestartet und automatisch eine Workflowinstanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-131">This will start the Counter WF service and automatically start a workflow instance.</span></span>  
  
5.  <span data-ttu-id="5bcbb-132">Wählen Sie alle Zeilen in der Sicht [dbo].[CounterService] in der Persistenzdatenbank aus (die Sicht wurde durch Ausführen von CreateInstanceStore.cmd in Schritt 1 hinzugefügt).</span><span class="sxs-lookup"><span data-stu-id="5bcbb-132">Quickly select all the rows in the [dbo].[CounterService] view in your persistence database (this view was added by running CreateInstanceStore.cmd in step 1).</span></span> <span data-ttu-id="5bcbb-133">Es wird ein Resultset ähnlich dem folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5bcbb-133">You will see a result set similar to the following:</span></span>  
  
    |<span data-ttu-id="5bcbb-134">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5bcbb-134">InstanceId</span></span>|<span data-ttu-id="5bcbb-135">CounterValue</span><span class="sxs-lookup"><span data-stu-id="5bcbb-135">CounterValue</span></span>|<span data-ttu-id="5bcbb-136">CounterValueLastUpdated</span><span class="sxs-lookup"><span data-stu-id="5bcbb-136">CounterValueLastUpdated</span></span>|  
    |----------------|------------------|-----------------------------|  
    |<span data-ttu-id="5bcbb-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span><span class="sxs-lookup"><span data-stu-id="5bcbb-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span></span>|<span data-ttu-id="5bcbb-138">12</span><span class="sxs-lookup"><span data-stu-id="5bcbb-138">12</span></span>|<span data-ttu-id="5bcbb-139">2010-02-18 22:48:01.740</span><span class="sxs-lookup"><span data-stu-id="5bcbb-139">2010-02-18 22:48:01.740</span></span>|  
  
     <span data-ttu-id="5bcbb-140">Wenn Sie die Sicht fortlaufend aktualisieren, werden Sie feststellen, dass sich der Wert von CounterValue und CounterValueLastUpdated alle zwei Sekunden ändert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-140">As you keep refreshing the view, you will notice that CounterValue and CounterValueLastUpdated change every two seconds.</span></span> <span data-ttu-id="5bcbb-141">Dies ist der Zeitabstand, in dem der Zähler automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-141">This is the interval at which the counter updates itself.</span></span> <span data-ttu-id="5bcbb-142">CounterValue und CounterValueLastUpdated entsprechen den höher gestuften Eigenschaften für diesen Workflow.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-142">CounterValue and CounterValueLastUpdated represent promoted properties for this workflow.</span></span>  
  
## <a name="to-remove-the-sample"></a><span data-ttu-id="5bcbb-143">So entfernen Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bcbb-143">To remove the sample</span></span>  
  
-   <span data-ttu-id="5bcbb-144">Führen Sie RemoveInstanceStore.cmd im Beispielverzeichnis (\WF\Basic\Persistence\PropertyPromotionActivity) aus.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-144">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity).</span></span>  
  
## <a name="understanding-this-sample"></a><span data-ttu-id="5bcbb-145">Grundlagen dieses Beispiels</span><span class="sxs-lookup"><span data-stu-id="5bcbb-145">Understanding This Sample</span></span>  
 <span data-ttu-id="5bcbb-146">Das Beispiel enthält zwei Projekte und eine SQL-Datei:</span><span class="sxs-lookup"><span data-stu-id="5bcbb-146">The sample contains two projects and an SQL file:</span></span>  
  
-   <span data-ttu-id="5bcbb-147">**CounterServiceApplication** ist eine Konsolenanwendung, die einen einfachen WF-Zählerdienst fungiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-147">**CounterServiceApplication** is a console application that hosts a simple Counter WF service.</span></span> <span data-ttu-id="5bcbb-148">Nach dem Erhalt einer unidirektionalen Nachricht über den `Start`-Endpunkt inkrementiert der Workflow alle zwei Sekunden eine Zählervariable und zählt so von 0 bis 29.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-148">Upon receiving a one-way message through the `Start` endpoint, the workflow counts from 0 to 29, incrementing a counter variable every two seconds.</span></span> <span data-ttu-id="5bcbb-149">Der Workflow wird nach jeder Erhöhung des Zählerwerts beibehalten, und die höher gestuften Eigenschaften werden in der Sicht [dbo].[CounterService] aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-149">After every counter increment, the workflow persists, and the promoted properties are updated in the [dbo].[CounterService] view.</span></span> <span data-ttu-id="5bcbb-150">Wenn Sie die Konsolenanwendung ausführen, wird der WF-Dienst gehostet. Eine Nachricht wird an den `Start`-Endpunkt gesendet, und es wird eine WF-Zählerinstanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-150">When the console application is run, it hosts the WF service and sends a message to the `Start` endpoint, creating a Counter WF instance.</span></span>  
  
-   <span data-ttu-id="5bcbb-151">**PropertyPromotionActivity** ist eine Klassenbibliothek, die den Konfigurationselementen, Workflowaktivitäten und workflowerweiterungen enthält, die die **CounterServiceApplication** verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-151">**PropertyPromotionActivity** is a class library that contains the configuration elements, workflow activities, and workflow extensions that the **CounterServiceApplication** uses.</span></span>  
  
-   <span data-ttu-id="5bcbb-152">**PropertyPromotionActivitySQLSample.sql** erstellt und fügt die Sicht [Dbo]. [ CounterService] in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-152">**PropertyPromotionActivitySQLSample.sql** creates and adds the view [dbo].[CounterService] to the database.</span></span>  
  
### <a name="counterserviceapplication"></a><span data-ttu-id="5bcbb-153">CounterServiceApplication</span><span class="sxs-lookup"><span data-stu-id="5bcbb-153">CounterServiceApplication</span></span>  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a><span data-ttu-id="5bcbb-154">Verwenden des SqlWorkflowInstanceStorePromotion-Konfigurationselements</span><span class="sxs-lookup"><span data-stu-id="5bcbb-154">Using the SqlWorkflowInstanceStorePromotion Configuration Element</span></span>  
 <span data-ttu-id="5bcbb-155">Das `SqlWorkflowInstanceStorePromotion`-Konfigurationselement erbt vom `SqlWorkflowInstanceStore`-Konfigurationselement, fügt jedoch das `promotionSets`-Konfigurationselement hinzu.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-155">The `SqlWorkflowInstanceStorePromotion` configuration element inherits from the `SqlWorkflowInstanceStore` configuration element, but adds an additional configuration element called `promotionSets`.</span></span> <span data-ttu-id="5bcbb-156">Das `promotionSets`-Element ermöglicht es dem Benutzer, höher gestufte Eigenschaften über die Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-156">The `promotionSets` element enables the user to specify promoted properties through configuration.</span></span> <span data-ttu-id="5bcbb-157">Die folgende Konfigurationsdatei wird im Beispiel verwendet:</span><span class="sxs-lookup"><span data-stu-id="5bcbb-157">This is the configuration file that is used by the sample:</span></span>  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 <span data-ttu-id="5bcbb-158">Überprüfen Sie die Definition für die Sicht [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="5bcbb-158">Examine the definition for the [dbo].[CounterService] view.</span></span>  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 <span data-ttu-id="5bcbb-159">Wenn eine Workflowinstanz beibehalten wird, wird in der `InstancePromotedProperties`-Sicht eine Zeile für jeden `PromotionSet` eingefügt, der in der Konfiguration definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-159">When a workflow instance persists, a row is inserted into the `InstancePromotedProperties` view for each `PromotionSet` defined in the configuration.</span></span> <span data-ttu-id="5bcbb-160">Diese Zeile enthält alle höher gestuften Eigenschaften des `PromotionSet` (eine höher gestufte Eigenschaft pro Spalte).</span><span class="sxs-lookup"><span data-stu-id="5bcbb-160">This row contains all the promoted properties of the `PromotionSet` (one promoted property per column).</span></span> <span data-ttu-id="5bcbb-161">Dieser `PromotionSet` wird nach folgendem Tupel sortiert: `InstanceId, PromotionName`.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-161">This `PromotionSet` is keyed by the tuple: `InstanceId, PromotionName`.</span></span> <span data-ttu-id="5bcbb-162">In diesem Beispiel wurde ein `PromotionSet` mit dem Namensattribut `CounterService` in der Konfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-162">In this sample, we have one `PromotionSet` defined in configuration whose name attribute is `CounterService`.</span></span> <span data-ttu-id="5bcbb-163">Beachten Sie, dass der Wert der `PromotionName`-Spalte dem Namensattribut des `PromotionSet`-Elements entspricht.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-163">Note how the `PromotionName` column value is equal to the name attribute of the `PromotionSet` element.</span></span>  
  
 <span data-ttu-id="5bcbb-164">Die Reihenfolge der `promotedValue`-Elemente korreliert mit der Platzierung der höher gestuften Eigenschaften in der `InstancePromotedProperties`-Sicht.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-164">The order of the `promotedValue` elements correlates with the placement of the promoted properties in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="5bcbb-165">`Count` stellt das erste `promotedValue`-Element dar.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-165">`Count` is the first `promotedValue` element.</span></span> <span data-ttu-id="5bcbb-166">Es wird daher der `Value1`-Spalte in der `InstancePromotedProperties`-Sicht zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-166">As a result, it is mapped to the `Value1` column in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="5bcbb-167">`LastIncrementedAt` stellt das zweite `promotedValue`-Element dar.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-167">`LastIncrementedAt` is the second `promotedValue` element.</span></span> <span data-ttu-id="5bcbb-168">Es wird daher der `Value2`-Spalte in der `InstancePromotedProperties`-Sicht zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-168">As a result, it is mapped to the `Value2` column in the `InstancePromotedProperties` view.</span></span>  
  
#### <a name="using-the-promotevalue-activity"></a><span data-ttu-id="5bcbb-169">Verwenden der PromoteValue-Aktivität</span><span class="sxs-lookup"><span data-stu-id="5bcbb-169">Using the PromoteValue Activity</span></span>  
 <span data-ttu-id="5bcbb-170">Untersuchen Sie die Datei CounterService.xamlx im [!INCLUDE[wf2](../../../../includes/wf2-md.md)]-Designer.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-170">Examine the CounterService.xamlx file in the [!INCLUDE[wf2](../../../../includes/wf2-md.md)] Designer.</span></span> <span data-ttu-id="5bcbb-171">Beachten Sie, dass die WF-Definition zwei spezielle Aktivitäten enthält: `PromoteValue<DateTime>` und `PromoteValue<Int32>`.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-171">Notice that there are two special activities in the WF definition: `PromoteValue<DateTime>` and `PromoteValue<Int32>`.</span></span>  
  
 <span data-ttu-id="5bcbb-172">Der `PromoteValue<Int32>`-Member der `Name`-Aktivität wurde als `Count` definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-172">The `PromoteValue<Int32>` activity has its `Name` member defined as `Count`.</span></span> <span data-ttu-id="5bcbb-173">Dies entspricht dem ersten `promotedValue`-Element in der Konfiguration. `Value` wurde als `Counter`-Workflowvariable definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-173">This matches with the first `promotedValue` element in the configuration, and has its `Value` defined as the `Counter` workflow variable.</span></span> <span data-ttu-id="5bcbb-174">Wenn der Workflow gespeichert wird, wird die `Counter`-Workflowvariable als höher gestufte Eigenschaft in der `Value1`-Spalte der `InstancePromotedProperties`-Sicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-174">When the workflow persists, the `Counter` workflow variable is persisted as a promoted property into the `Value1` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="5bcbb-175">Der `PromoteValue<DateTime>`-Member der `Name`-Aktivität wurde als `LastIncrementedAt` definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-175">The `PromoteValue<DateTime>` activity has its `Name` member defined as `LastIncrementedAt`.</span></span> <span data-ttu-id="5bcbb-176">Dies entspricht dem zweiten `promotedValue`-Element in der Konfiguration. `Value` wurde als `TimeLastIncremented`-Workflowvariable definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-176">This matches with the second `promotedValue` element in the configuration, and has its `Value` defined as the `TimeLastIncremented` workflow variable.</span></span> <span data-ttu-id="5bcbb-177">Wenn der Workflow beibehalten wird, wird daher der Wert für die `TimeLastIncremented`-Workflowvariable als höher gestufte Eigenschaft in der `Value2`-Spalte der `InstancePromotedProperties`-Sicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-177">This means that when the workflow persists, the value for the `TimeLastIncremented` workflow variable will be persisted as a promoted property into the `Value2` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="5bcbb-178">Beachten Sie, dass die `PromotedValue`-Aktivität außerdem über den booleschen Member `ClearExistingPromotedData` verfügt.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-178">Note that the `PromotedValue` activity also has a Boolean member called `ClearExistingPromotedData`.</span></span> <span data-ttu-id="5bcbb-179">Wenn dieser Member auf `true` festgelegt wird, werden alle höher gestuften Eigenschaftswerte bis zu diesem Punkt im Workflow bereinigt.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-179">When this member is set to `true`, this clears all the promoted property values up to that point in the workflow.</span></span> <span data-ttu-id="5bcbb-180">Beispielsweise ist eine Sequence-Aktivität wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="5bcbb-180">For example, if a Sequence activity is defined as follows:</span></span>  
  
1.  <span data-ttu-id="5bcbb-181">PromoteValue {Name = "Count", Value = 3}</span><span class="sxs-lookup"><span data-stu-id="5bcbb-181">PromoteValue { Name = "Count", Value = 3}</span></span>  
  
2.  <span data-ttu-id="5bcbb-182">PromoteValue {Name = "LastIncrementedAt", Wert = 1-1-2000}</span><span class="sxs-lookup"><span data-stu-id="5bcbb-182">PromoteValue {Name = "LastIncrementedAt", Value = 1-1-2000 }</span></span>  
  
3.  <span data-ttu-id="5bcbb-183">Beibehalten</span><span class="sxs-lookup"><span data-stu-id="5bcbb-183">Persist</span></span>  
  
4.  <span data-ttu-id="5bcbb-184">PromoteValue {Name = "Count", Wert = 4, ClearExistingPromotedData = "true"}</span><span class="sxs-lookup"><span data-stu-id="5bcbb-184">PromoteValue {Name = "Count", Value = 4, ClearExistingPromotedData = true}</span></span>  
  
5.  <span data-ttu-id="5bcbb-185">Beibehalten</span><span class="sxs-lookup"><span data-stu-id="5bcbb-185">Persist</span></span>  
  
 <span data-ttu-id="5bcbb-186">Bei der zweiten persistenten Speicherung wird der Wert für `Count` auf 4 erhöht.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-186">On the second persist, the promoted value for `Count` will be 4.</span></span> <span data-ttu-id="5bcbb-187">Allerdings die höher gestufte Wert für `LastIncrementedAt` werden `NULL`.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-187">However, the promoted value for `LastIncrementedAt` will be `NULL`.</span></span> <span data-ttu-id="5bcbb-188">Wenn `ClearExistingPromotedData` in Schritt 4 nicht auf `true` festgelegt worden wäre, würde der höher gestufte Wert für Count nach der zweiten persistenten Speicherung 4 lauten.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-188">If `ClearExistingPromotedData` was not set to `true` for step 4, then after the second persist, the promoted value for Count would be 4.</span></span> <span data-ttu-id="5bcbb-189">Demzufolge wäre der höher gestufte Wert für `LastIncrementedAt` weiterhin 1-1-2000.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-189">As a result, the promoted value for `LastIncrementedAt` would still be 1-1-2000.</span></span>  
  
### <a name="propertypromotionactivity"></a><span data-ttu-id="5bcbb-190">PropertyPromotionActivity</span><span class="sxs-lookup"><span data-stu-id="5bcbb-190">PropertyPromotionActivity</span></span>  
 <span data-ttu-id="5bcbb-191">Diese Klassenbibliothek enthält die folgenden öffentlichen Klassen, um die Verwendung der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Funktion zur Höherstufung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-191">This class library contains the following public classes to simplify use of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature.</span></span>  
  
#### <a name="promotevalue-class"></a><span data-ttu-id="5bcbb-192">PromoteValue-Klasse</span><span class="sxs-lookup"><span data-stu-id="5bcbb-192">PromoteValue Class</span></span>  
 <span data-ttu-id="5bcbb-193">Mit dieser Klasse wird eine Eigenschaft höher gestuft.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-193">This class promotes one property.</span></span> <span data-ttu-id="5bcbb-194">Der Name der höher gestuften Eigenschaft sollte mit dem Namensattribut eines `promotedValue`-Elements in der Konfiguration übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-194">The name of the promoted property should match a name attribute of a `promotedValue` element in the configuration.</span></span> <span data-ttu-id="5bcbb-195">Diese Aktivität kann im Workflow-Designer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-195">This activity can be used in the Workflow Designer.</span></span> <span data-ttu-id="5bcbb-196">Ein Beispiel zur Verwendung finden Sie in der CounterServiceApplication.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-196">See the CounterServiceApplication for an example usage.</span></span>  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 <span data-ttu-id="5bcbb-197">ClearExistingPromotedData (Boolescher Wert)</span><span class="sxs-lookup"><span data-stu-id="5bcbb-197">ClearExistingPromotedData (Bool)</span></span>  
 <span data-ttu-id="5bcbb-198">Löscht alle Werte, die vor dieser Aktivität höher gestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-198">Clears all values that were promoted before this activity.</span></span>  
  
 <span data-ttu-id="5bcbb-199">Name (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="5bcbb-199">Name (string)</span></span>  
 <span data-ttu-id="5bcbb-200">Der Name, der diese Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-200">The name that represents this property.</span></span> <span data-ttu-id="5bcbb-201">Dies sollte das Namensattribut des entsprechen einem \<PromotedValue >-Elements in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-201">This should match the name attribute of a \<promotedValue> element in the configuration.</span></span>  
  
 <span data-ttu-id="5bcbb-202">Wert (InArgument\<T >)</span><span class="sxs-lookup"><span data-stu-id="5bcbb-202">Value (InArgument\<T>)</span></span>  
 <span data-ttu-id="5bcbb-203">Die Variable/der Wert, die bzw. der in der Spalte gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-203">The variable / value that you want to store in the column.</span></span>  
  
#### <a name="promotevalues-class"></a><span data-ttu-id="5bcbb-204">PromoteValues-Klasse</span><span class="sxs-lookup"><span data-stu-id="5bcbb-204">PromoteValues Class</span></span>  
 <span data-ttu-id="5bcbb-205">Stuft mehrere Eigenschaften hoch.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-205">Promotes multiple properties.</span></span> <span data-ttu-id="5bcbb-206">Die Namen der höher gestuften Eigenschaften sollten mit allen Namensattributen der `promotedValue`-Elemente in der Konfiguration übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-206">The names of the promoted properties should match all name attributes in the `promotedValue` elements in the configuration.</span></span> <span data-ttu-id="5bcbb-207">Die Verwendung erfolgt analog zur `PromoteValue`-Aktivität, mit dem Unterschied, dass mehrere Eigenschaften auf einmal höher gestuft werden können.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-207">Usage is similar to the `PromoteValue` activity, except for the fact that multiple properties can be promoted at the same time.</span></span> <span data-ttu-id="5bcbb-208">Diese Aktivität kann nicht im Workflow-Designer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-208">This activity cannot be used in the Workflow Designer.</span></span>  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a><span data-ttu-id="5bcbb-209">SqlWorkflowInstanceStorePromotionBehavior</span><span class="sxs-lookup"><span data-stu-id="5bcbb-209">SqlWorkflowInstanceStorePromotionBehavior</span></span>  
 <span data-ttu-id="5bcbb-210">Wird von `SqlWorkflowInstanceStoreBehavior` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-210">Derives from `SqlWorkflowInstanceStoreBehavior`.</span></span> <span data-ttu-id="5bcbb-211">Mit dieser abgeleiteten Klasse wird ein benutzerdefinierter Persistenzteilnehmer (ebenfalls Teil dieser Bibliothek) als Workflowerweiterung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-211">This derived class adds a custom persistence participant (also a part of this library) as a workflow extension.</span></span> <span data-ttu-id="5bcbb-212">Die Implementierung der beiden vorherigen Workflowaktivitäten ist von diesem benutzerdefinierten Persistenzteilnehmer abhängig.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-212">The implementation of the previous two workflow activities relies on this custom persistence participant.</span></span>  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 <span data-ttu-id="5bcbb-213">Diese Klassenbibliothek enthält auch die `ConfigurationElement`-Implementierung für das `SqlWorkflowInstanceStorePromotionElement` sowie einen benutzerdefinierten Persistenzteilnehmer, der von den vorherigen Aktivitäten zur Höherstufung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-213">This class library also contains the `ConfigurationElement` implementation for the `SqlWorkflowInstanceStorePromotionElement` and a custom persistence participant used by the previous promotion activities.</span></span>  
  
### <a name="propertypromotionactivitysqlsample"></a><span data-ttu-id="5bcbb-214">PropertyPromotionActivitySQLSample</span><span class="sxs-lookup"><span data-stu-id="5bcbb-214">PropertyPromotionActivitySQLSample</span></span>  
 <span data-ttu-id="5bcbb-215">Mit dieser SQL-Datei wird eine `[dbo].[CounterService]`-Sicht zusätzlich zur `[InstancePromotedProperties]`-Sicht erstellt, um alle Instanzen mit einem CounterService-Satz für die Höherstufung abzufragen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-215">This SQL file creates a `[dbo].[CounterService]` view in addition to the `[InstancePromotedProperties]` view for querying all instances that have a CounterService Promotion set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5bcbb-216">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-216">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5bcbb-217">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="5bcbb-217">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5bcbb-218">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5bcbb-218">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5bcbb-219">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="5bcbb-219">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a><span data-ttu-id="5bcbb-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bcbb-220">See Also</span></span>  
 [<span data-ttu-id="5bcbb-221">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="5bcbb-221">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
