---
title: Verwenden von WorkflowIdentity und Versionsverwaltung
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: f7e66d1827c5224ab97faeceaedc6ec0532a1923
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661214"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="8df02-102">Verwenden von WorkflowIdentity und Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="8df02-102">Using WorkflowIdentity and Versioning</span></span>

<span data-ttu-id="8df02-103"><xref:System.Activities.WorkflowIdentity> bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Workflowdefinition einen Namen und eine <xref:System.Version> zuzuweisen und diese Informationen einer persistenten Workflowinstanz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8df02-103"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="8df02-104">Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="8df02-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="8df02-105">Dieses Thema bietet eine Übersicht über die Verwendung von <xref:System.Activities.WorkflowIdentity> mit <xref:System.Activities.WorkflowApplication>-Hosting.</span><span class="sxs-lookup"><span data-stu-id="8df02-105">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="8df02-106">Weitere Informationen zur Seite-an-Seite-Ausführung von workflowdefinitionen in einem Workflowdienst, finden Sie unter [parallele Versionsverwaltung in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span><span class="sxs-lookup"><span data-stu-id="8df02-106">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="8df02-107">Weitere Informationen zu dynamischen Updates finden Sie unter [dynamische Updates](dynamic-update.md).</span><span class="sxs-lookup"><span data-stu-id="8df02-107">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="8df02-108">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="8df02-108">In this topic</span></span>

- [<span data-ttu-id="8df02-109">Verwenden von WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="8df02-109">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [<span data-ttu-id="8df02-110">Seite-an-Seite-Ausführung mit WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="8df02-110">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)

- [<span data-ttu-id="8df02-111">Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflowversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="8df02-111">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [<span data-ttu-id="8df02-112">Das Datenbankschema aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8df02-112">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a> <span data-ttu-id="8df02-113">Verwenden von WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="8df02-113">Using WorkflowIdentity</span></span>

<span data-ttu-id="8df02-114">Um <xref:System.Activities.WorkflowIdentity> zu verwenden, erstellen Sie eine Instanz, konfigurieren diese und ordnen sie einer <xref:System.Activities.WorkflowApplication>-Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="8df02-114">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="8df02-115">Eine <xref:System.Activities.WorkflowIdentity>-Instanz enthält drei identifizierende Informationen.</span><span class="sxs-lookup"><span data-stu-id="8df02-115">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="8df02-116"><xref:System.Activities.WorkflowIdentity.Name%2A> und <xref:System.Activities.WorkflowIdentity.Version%2A> enthalten einen Namen und eine <xref:System.Version> und sind erforderlich. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und kann verwendet werden, um eine zusätzliche Zeichenfolge anzugeben, die Informationen wie den Assemblynamen oder andere gewünschte Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="8df02-116"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="8df02-117"><xref:System.Activities.WorkflowIdentity> ist eindeutig, wenn jede ihrer drei Eigenschaften sich von einer anderen <xref:System.Activities.WorkflowIdentity> unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="8df02-117">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8df02-118"><xref:System.Activities.WorkflowIdentity> sollte keine persönlich identifizierbaren Informationen (PII) enthalten.</span><span class="sxs-lookup"><span data-stu-id="8df02-118">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="8df02-119">Informationen über die <xref:System.Activities.WorkflowIdentity>-Aktivität, mit der eine Instanz erstellt wird, werden von der Laufzeit zu verschiedenen Zeiten des Aktivitätslebenszyklus an alle konfigurierten Überwachungsdienste ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8df02-119">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="8df02-120">Die WF-Nachverfolgung besitzt keinen Mechanismus, um PII (vertrauliche Benutzerdaten) auszublenden.</span><span class="sxs-lookup"><span data-stu-id="8df02-120">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="8df02-121">Daher sollte eine <xref:System.Activities.WorkflowIdentity>-Instanz keine PII-Daten enthalten, die möglicherweise von der Laufzeit in die Überwachungsdatensätze ausgegeben werden und so für jede Person mit Anzeigerechten für Überwachungsdatensätze sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="8df02-121">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>

<span data-ttu-id="8df02-122">Im folgenden Beispiel wird <xref:System.Activities.WorkflowIdentity> erstellt und einer Instanz eines Workflows zugeordnet, der mit einer `MortgageWorkflow`-Workflowdefinition erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8df02-122">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="8df02-123">Beim erneuten Laden und Fortsetzen eines Workflows muss eine <xref:System.Activities.WorkflowIdentity> verwendet werden, die in Übereinstimmung mit der <xref:System.Activities.WorkflowIdentity> der persistenten Workflowinstanz konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="8df02-123">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="8df02-124">Wenn die beim erneuten Laden der Workflowinstanz verwendete <xref:System.Activities.WorkflowIdentity> nicht mit der persistenten <xref:System.Activities.WorkflowIdentity> übereinstimmt, wird <xref:System.Activities.VersionMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8df02-124">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="8df02-125">Im folgenden Beispiel wird versucht, die `MortgageWorkflow`-Instanz zu laden, die im vorherigen Beispiel persistent gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="8df02-125">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="8df02-126">Dieser Ladeversuch wird mithilfe einer <xref:System.Activities.WorkflowIdentity> ausgeführt, die für eine neuere Version des Hypothekenworkflows konfiguriert wurde, die nicht der persistenten Instanz entspricht.</span><span class="sxs-lookup"><span data-stu-id="8df02-126">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="8df02-127">Beim Ausführen des vorangehenden Codes wird folgende <xref:System.Activities.VersionMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8df02-127">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>

```
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a> <span data-ttu-id="8df02-128">Seite-an-Seite-Ausführung mit WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="8df02-128">Side-by-side Execution using WorkflowIdentity</span></span>

<span data-ttu-id="8df02-129"><xref:System.Activities.WorkflowIdentity> kann verwendet werden, um die parallele Ausführung mehrerer Workflowversionen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="8df02-129"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="8df02-130">Ein häufiges Szenario besteht darin, die Geschäftsanforderungen in einem Workflow mit langer Laufzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8df02-130">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="8df02-131">Bei der Bereitstellung einer aktualisierten Version können viele Instanzen eines Workflows ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8df02-131">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="8df02-132">Die Hostanwendung kann so konfiguriert werden, dass die aktualisierte Workflowdefinition beim Starten neuer Instanzen verwendet wird, und sie muss dafür sorgen, beim Fortsetzen von Instanzen die richtige Workflowdefinition bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8df02-132">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="8df02-133"><xref:System.Activities.WorkflowIdentity> kann verwendet werden, um beim Fortsetzen von Workflowinstanzen die entsprechende Workflowdefinition zu identifizieren und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8df02-133"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>

<span data-ttu-id="8df02-134">Um die <xref:System.Activities.WorkflowIdentity> einer persistenten Workflowinstanz abzurufen, wird die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="8df02-134">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="8df02-135">Die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet die <xref:System.Activities.WorkflowApplication.Id%2A> der persistenten Workflowinstanz und den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, der die persistente Instanz enthält und <xref:System.Activities.WorkflowApplicationInstance> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8df02-135">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="8df02-136"><xref:System.Activities.WorkflowApplicationInstance> enthält Informationen über eine persistente Workflowinstanz, einschließlich der zugeordneten <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="8df02-136">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="8df02-137">Diese zugeordnete <xref:System.Activities.WorkflowIdentity> kann vom Host verwendet werden, um die richtige Workflowdefinition bereitzustellen, wenn die Workflowinstanz geladen und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="8df02-137">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>

> [!NOTE]
> <span data-ttu-id="8df02-138">Eine leere <xref:System.Activities.WorkflowIdentity> ist gültig und kann vom Host verwendet werden, um Instanzen, die ohne zugeordnete <xref:System.Activities.WorkflowIdentity> gespeichert wurden, der richtigen Workflowdefinition zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8df02-138">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="8df02-139">Dieses Szenario tritt auf, wenn eine Workflowanwendung zunächst ohne Workflowversionsverwaltung geschrieben wurde oder wenn eine Anwendung von [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="8df02-139">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="8df02-140">Weitere Informationen finden Sie unter [Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung Workflowversionsverwaltung](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span><span class="sxs-lookup"><span data-stu-id="8df02-140">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>

<span data-ttu-id="8df02-141">Im folgenden Beispiel eine `Dictionary<WorkflowIdentity, Activity>` wird zum Zuordnen <xref:System.Activities.WorkflowIdentity> -Instanzen mit die entsprechenden workflowdefinitionen und ein Workflow gestartet wird, mithilfe der `MortgageWorkflow` Workflowdefinition zugeordnet ist die `identityV1` <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="8df02-141">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowIdentity identityV2 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v2",
    Version = new Version(2, 0, 0, 0)
};

Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="8df02-142">Im folgenden Beispiel werden Informationen über die persistente Workflowinstanz aus dem vorherigen Beispiel abgerufen, indem <xref:System.Activities.WorkflowApplication.GetInstance%2A> aufgerufen wird, und die persistenten <xref:System.Activities.WorkflowIdentity>-Informationen werden verwendet, um die entsprechende Workflowdefinition abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8df02-142">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="8df02-143">Diese Informationen werden verwendet, um <xref:System.Activities.WorkflowApplication> zu konfigurieren. Der Workflow wird daraufhin geladen.</span><span class="sxs-lookup"><span data-stu-id="8df02-143">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="8df02-144">Da die <xref:System.Activities.WorkflowApplication.Load%2A>-Überladung, die <xref:System.Activities.WorkflowApplicationInstance> annimmt, verwendet wird, wird von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> der für <xref:System.Activities.WorkflowApplicationInstance> konfigurierte <xref:System.Activities.WorkflowApplication> verwendet, sodass die zugehörige <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft nicht konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="8df02-144">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>

> [!NOTE]
>  <span data-ttu-id="8df02-145">Wenn die <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft festgelegt wird, muss sie mit derselben <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Instanz festgelegt werden, die von <xref:System.Activities.WorkflowApplicationInstance> verwendet wird, da andernfalls <xref:System.ArgumentException> mit der folgenden Meldung ausgelöst wird: `The instance is configured with a different InstanceStore than this WorkflowApplication.`</span><span class="sxs-lookup"><span data-stu-id="8df02-145">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>

```csharp
// Get the WorkflowApplicationInstance of the desired workflow from the specified
// SqlWorkflowInstanceStore.
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);

// Use the persisted WorkflowIdentity to retrieve the correct workflow
// definition from the dictionary.
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];

WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(instance);

// Resume the workflow...
```

## <a name="UpdatingWF4PersistenceDatabases"></a> <span data-ttu-id="8df02-146">Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflowversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="8df02-146">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>

<span data-ttu-id="8df02-147">Ein SqlWorkflowInstanceStoreSchemaUpgrade.sql-Datenbankskript wird bereitgestellt, um ein Upgrade für Persistenzdatenbanken auszuführen, die mit [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]-Datenbankskripts erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="8df02-147">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] database scripts.</span></span> <span data-ttu-id="8df02-148">Dieses Skript aktualisiert die Datenbanken aus, um die neuen versionsverwaltungsfunktionen eingeführt, die in .NET Framework 4.5 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8df02-148">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="8df02-149">Den persistenten Workflowinstanzen in den Datenbanken werden Standardversionswerte zugeordnet, und sie können an einer parallelen Ausführung und an dynamischen Updates beteiligt sein.</span><span class="sxs-lookup"><span data-stu-id="8df02-149">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>

<span data-ttu-id="8df02-150">Wenn eine .NET Framework 4.5-Workflow-Anwendung auf einen beliebigen persistenzvorgang auszuführen versucht, die die neuen versionsverwaltungsfunktionen für eine Persistenzdatenbank verwenden, die nicht mithilfe der bereitgestellten Skripts aktualisiert wurde ein <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> ausgelöst und eine Meldung ähnlich der folgende Meldung.</span><span class="sxs-lookup"><span data-stu-id="8df02-150">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>

```
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a> <span data-ttu-id="8df02-151">Das Datenbankschema aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8df02-151">To upgrade the database schema</span></span>

1. <span data-ttu-id="8df02-152">Öffnen Sie SQL Server Management Studio und verbinden Sie mit dem Persistenzdatenbank-Server, z. B. **. \SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="8df02-152">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>

2. <span data-ttu-id="8df02-153">Wählen Sie **öffnen**, **Datei** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="8df02-153">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="8df02-154">Wechseln Sie zum folgenden Ordner: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="8df02-154">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span></span>

3. <span data-ttu-id="8df02-155">Wählen Sie **SqlWorkflowInstanceStoreSchemaUpgrade.sql** , und klicken Sie auf **öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8df02-155">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>

4. <span data-ttu-id="8df02-156">Wählen Sie den Namen der Persistenzdatenbank in der **verfügbaren Datenbanken** Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="8df02-156">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>

5. <span data-ttu-id="8df02-157">Wählen Sie **Execute** aus der **Abfrage** Menü.</span><span class="sxs-lookup"><span data-stu-id="8df02-157">Choose **Execute** from the **Query** menu.</span></span>

<span data-ttu-id="8df02-158">Sobald die Abfrage abgeschlossen ist, wird das Datenbankschema aktualisiert. Sie können jetzt die standardmäßige Workflowidentität anzeigen, die den persistenten Workflowinstanzen zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="8df02-158">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="8df02-159">Erweitern Sie die Persistenzdatenbank in der **Datenbanken** Knoten die **Objekt-Explorer**, und erweitern Sie dann die **Ansichten** Knoten.</span><span class="sxs-lookup"><span data-stu-id="8df02-159">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="8df02-160">Mit der rechten Maustaste **System.Activities.DurableInstancing.Instances** , und wählen Sie **oberste 1000 Zeilen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8df02-160">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="8df02-161">Einen Bildlauf zum Ende der Spalten aus, und beachten Sie, dass sechs zusätzliche Spalten der Sicht hinzugefügt: **IdentityName**, **IdentityPackage**, **erstellen**, **wichtigen**, **kleinere**, und **Revision**.</span><span class="sxs-lookup"><span data-stu-id="8df02-161">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="8df02-162">Alle persistenten Workflows weisen den Wert **NULL** für diese Felder, die eine leere workflowidentität hinweist darstellt.</span><span class="sxs-lookup"><span data-stu-id="8df02-162">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
