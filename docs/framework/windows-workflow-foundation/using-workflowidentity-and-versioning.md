---
title: Verwenden von WorkflowIdentity und Versionsverwaltung
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 66ef4fed682554d9fab2a7b0f85bb9cfaf8e8a29
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74142048"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="d6363-102">Verwenden von WorkflowIdentity und Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d6363-102">Using WorkflowIdentity and Versioning</span></span>

<span data-ttu-id="d6363-103"><xref:System.Activities.WorkflowIdentity> bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Workflowdefinition einen Namen und eine <xref:System.Version> zuzuweisen und diese Informationen einer persistenten Workflowinstanz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d6363-103"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="d6363-104">Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="d6363-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="d6363-105">Dieses Thema bietet eine Übersicht über die Verwendung von <xref:System.Activities.WorkflowIdentity> mit <xref:System.Activities.WorkflowApplication>-Hosting.</span><span class="sxs-lookup"><span data-stu-id="d6363-105">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="d6363-106">Informationen zur parallelen Ausführung von Workflow Definitionen in einem Workflow Dienst finden Sie unter parallele [Versionsverwaltung in](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md)Workflow Service Host.</span><span class="sxs-lookup"><span data-stu-id="d6363-106">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="d6363-107">Weitere Informationen zum dynamischen Update finden Sie unter [dynamisches Update](dynamic-update.md).</span><span class="sxs-lookup"><span data-stu-id="d6363-107">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="d6363-108">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="d6363-108">In this topic</span></span>

- [<span data-ttu-id="d6363-109">Verwenden von workflowidentity</span><span class="sxs-lookup"><span data-stu-id="d6363-109">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [<span data-ttu-id="d6363-110">Parallele Ausführung mithilfe von workflowidentity</span><span class="sxs-lookup"><span data-stu-id="d6363-110">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)

- [<span data-ttu-id="d6363-111">Aktualisieren von .NET Framework 4 Persistenzdatenbanken zur Unterstützung der Workflow Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d6363-111">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [<span data-ttu-id="d6363-112">So aktualisieren Sie das Datenbankschema</span><span class="sxs-lookup"><span data-stu-id="d6363-112">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a><span data-ttu-id="d6363-113">Verwenden von workflowidentity</span><span class="sxs-lookup"><span data-stu-id="d6363-113">Using WorkflowIdentity</span></span>

<span data-ttu-id="d6363-114">Um <xref:System.Activities.WorkflowIdentity> zu verwenden, erstellen Sie eine Instanz, konfigurieren diese und ordnen sie einer <xref:System.Activities.WorkflowApplication>-Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="d6363-114">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="d6363-115">Eine <xref:System.Activities.WorkflowIdentity>-Instanz enthält drei identifizierende Informationen.</span><span class="sxs-lookup"><span data-stu-id="d6363-115">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="d6363-116"><xref:System.Activities.WorkflowIdentity.Name%2A> und <xref:System.Activities.WorkflowIdentity.Version%2A> enthalten einen Namen und eine <xref:System.Version> und sind erforderlich. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und kann verwendet werden, um eine zusätzliche Zeichenfolge anzugeben, die Informationen wie den Assemblynamen oder andere gewünschte Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="d6363-116"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="d6363-117"><xref:System.Activities.WorkflowIdentity> ist eindeutig, wenn jede ihrer drei Eigenschaften sich von einer anderen <xref:System.Activities.WorkflowIdentity> unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="d6363-117">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6363-118"><xref:System.Activities.WorkflowIdentity> sollte keine persönlich identifizierbaren Informationen (PII) enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6363-118">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="d6363-119">Informationen über die <xref:System.Activities.WorkflowIdentity>-Aktivität, mit der eine Instanz erstellt wird, werden von der Laufzeit zu verschiedenen Zeiten des Aktivitätslebenszyklus an alle konfigurierten Überwachungsdienste ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6363-119">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="d6363-120">Die WF-Nachverfolgung besitzt keinen Mechanismus, um PII (vertrauliche Benutzerdaten) auszublenden.</span><span class="sxs-lookup"><span data-stu-id="d6363-120">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="d6363-121">Daher sollte eine <xref:System.Activities.WorkflowIdentity>-Instanz keine PII-Daten enthalten, die möglicherweise von der Laufzeit in die Überwachungsdatensätze ausgegeben werden und so für jede Person mit Anzeigerechten für Überwachungsdatensätze sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="d6363-121">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>

<span data-ttu-id="d6363-122">Im folgenden Beispiel wird <xref:System.Activities.WorkflowIdentity> erstellt und einer Instanz eines Workflows zugeordnet, der mit einer `MortgageWorkflow`-Workflowdefinition erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6363-122">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>

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

<span data-ttu-id="d6363-123">Beim erneuten Laden und Fortsetzen eines Workflows muss eine <xref:System.Activities.WorkflowIdentity> verwendet werden, die in Übereinstimmung mit der <xref:System.Activities.WorkflowIdentity> der persistenten Workflowinstanz konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d6363-123">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="d6363-124">Wenn die beim erneuten Laden der Workflowinstanz verwendete <xref:System.Activities.WorkflowIdentity> nicht mit der persistenten <xref:System.Activities.WorkflowIdentity> übereinstimmt, wird <xref:System.Activities.VersionMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d6363-124">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="d6363-125">Im folgenden Beispiel wird versucht, die `MortgageWorkflow`-Instanz zu laden, die im vorherigen Beispiel persistent gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6363-125">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="d6363-126">Dieser Ladeversuch wird mithilfe einer <xref:System.Activities.WorkflowIdentity> ausgeführt, die für eine neuere Version des Hypothekenworkflows konfiguriert wurde, die nicht der persistenten Instanz entspricht.</span><span class="sxs-lookup"><span data-stu-id="d6363-126">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="d6363-127">Beim Ausführen des vorangehenden Codes wird folgende <xref:System.Activities.VersionMismatchException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d6363-127">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>

```
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a><span data-ttu-id="d6363-128">Parallele Ausführung mithilfe von workflowidentity</span><span class="sxs-lookup"><span data-stu-id="d6363-128">Side-by-side Execution using WorkflowIdentity</span></span>

<span data-ttu-id="d6363-129"><xref:System.Activities.WorkflowIdentity> kann verwendet werden, um die parallele Ausführung mehrerer Workflowversionen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="d6363-129"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="d6363-130">Ein häufiges Szenario besteht darin, die Geschäftsanforderungen in einem Workflow mit langer Laufzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d6363-130">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="d6363-131">Bei der Bereitstellung einer aktualisierten Version können viele Instanzen eines Workflows ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6363-131">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="d6363-132">Die Hostanwendung kann so konfiguriert werden, dass die aktualisierte Workflowdefinition beim Starten neuer Instanzen verwendet wird, und sie muss dafür sorgen, beim Fortsetzen von Instanzen die richtige Workflowdefinition bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6363-132">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="d6363-133"><xref:System.Activities.WorkflowIdentity> kann verwendet werden, um beim Fortsetzen von Workflowinstanzen die entsprechende Workflowdefinition zu identifizieren und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6363-133"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>

<span data-ttu-id="d6363-134">Um die <xref:System.Activities.WorkflowIdentity> einer persistenten Workflowinstanz abzurufen, wird die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6363-134">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="d6363-135">Die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet die <xref:System.Activities.WorkflowApplication.Id%2A> der persistenten Workflowinstanz und den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, der die persistente Instanz enthält und <xref:System.Activities.WorkflowApplicationInstance> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d6363-135">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="d6363-136"><xref:System.Activities.WorkflowApplicationInstance> enthält Informationen über eine persistente Workflowinstanz, einschließlich der zugeordneten <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="d6363-136">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="d6363-137">Diese zugeordnete <xref:System.Activities.WorkflowIdentity> kann vom Host verwendet werden, um die richtige Workflowdefinition bereitzustellen, wenn die Workflowinstanz geladen und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d6363-137">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>

> [!NOTE]
> <span data-ttu-id="d6363-138">Eine leere <xref:System.Activities.WorkflowIdentity> ist gültig und kann vom Host verwendet werden, um Instanzen, die ohne zugeordnete <xref:System.Activities.WorkflowIdentity> gespeichert wurden, der richtigen Workflowdefinition zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d6363-138">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="d6363-139">Dieses Szenario kann auftreten, wenn eine Workflow Anwendung nicht anfänglich mit der Workflow Versionsverwaltung geschrieben wurde oder wenn eine Anwendung von .NET Framework 4 aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d6363-139">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from .NET Framework 4.</span></span> <span data-ttu-id="d6363-140">Weitere Informationen finden [Sie unter Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflow Versions](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="d6363-140">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>

<span data-ttu-id="d6363-141">Im folgenden Beispiel wird eine `Dictionary<WorkflowIdentity, Activity>` verwendet, um <xref:System.Activities.WorkflowIdentity>-Instanzen den entsprechenden Workflow Definitionen zuzuordnen, und ein Workflow wird mit der `MortgageWorkflow` Workflow Definition gestartet, die dem `identityV1` <xref:System.Activities.WorkflowIdentity>zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d6363-141">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>

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

<span data-ttu-id="d6363-142">Im folgenden Beispiel werden Informationen über die persistente Workflowinstanz aus dem vorherigen Beispiel abgerufen, indem <xref:System.Activities.WorkflowApplication.GetInstance%2A> aufgerufen wird, und die persistenten <xref:System.Activities.WorkflowIdentity>-Informationen werden verwendet, um die entsprechende Workflowdefinition abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d6363-142">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="d6363-143">Diese Informationen werden verwendet, um <xref:System.Activities.WorkflowApplication> zu konfigurieren. Der Workflow wird daraufhin geladen.</span><span class="sxs-lookup"><span data-stu-id="d6363-143">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="d6363-144">Da die <xref:System.Activities.WorkflowApplication.Load%2A>-Überladung, die <xref:System.Activities.WorkflowApplicationInstance> annimmt, verwendet wird, wird von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> der für <xref:System.Activities.WorkflowApplicationInstance> konfigurierte <xref:System.Activities.WorkflowApplication> verwendet, sodass die zugehörige <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft nicht konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="d6363-144">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>

> [!NOTE]
> <span data-ttu-id="d6363-145">Wenn die <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft festgelegt wird, muss sie mit derselben <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Instanz festgelegt werden, die von <xref:System.Activities.WorkflowApplicationInstance> verwendet wird, da andernfalls <xref:System.ArgumentException> mit der folgenden Meldung ausgelöst wird: `The instance is configured with a different InstanceStore than this WorkflowApplication.`</span><span class="sxs-lookup"><span data-stu-id="d6363-145">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>

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

## <a name="UpdatingWF4PersistenceDatabases"></a><span data-ttu-id="d6363-146">Aktualisieren von .NET Framework 4 Persistenzdatenbanken zur Unterstützung der Workflow Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d6363-146">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>

<span data-ttu-id="d6363-147">Ein sqlworkflowinstancestoreschemaupgrade. SQL-Datenbankskript wird zur Aktualisierung von Persistenzdatenbanken bereitgestellt, die mit den .NET Framework 4-Daten Bank Skripts erstellt</span><span class="sxs-lookup"><span data-stu-id="d6363-147">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the .NET Framework 4 database scripts.</span></span> <span data-ttu-id="d6363-148">Dieses Skript aktualisiert die Datenbanken, um die neuen Versions Verwaltungsfunktionen zu unterstützen, die in .NET Framework 4,5 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="d6363-148">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="d6363-149">Den persistenten Workflowinstanzen in den Datenbanken werden Standardversionswerte zugeordnet, und sie können an einer parallelen Ausführung und an dynamischen Updates beteiligt sein.</span><span class="sxs-lookup"><span data-stu-id="d6363-149">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>

<span data-ttu-id="d6363-150">Wenn eine .NET Framework 4,5-Workflow Anwendung alle Persistenzvorgänge versucht, die die neuen Versions Verwaltungsfunktionen für eine Persistenzdatenbank verwenden, die nicht mit dem bereitgestellten Skript aktualisiert wurde, wird eine-<xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> mit einer Meldung ausgelöst, die der folgenden Meldung ähnelt:</span><span class="sxs-lookup"><span data-stu-id="d6363-150">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>

```
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a><span data-ttu-id="d6363-151">So aktualisieren Sie das Datenbankschema</span><span class="sxs-lookup"><span data-stu-id="d6363-151">To upgrade the database schema</span></span>

1. <span data-ttu-id="d6363-152">Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit dem persistenzdatenbankserver her, z.b. **.\sqlexpress**</span><span class="sxs-lookup"><span data-stu-id="d6363-152">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>

2. <span data-ttu-id="d6363-153">Wählen Sie im Menü **Datei** die Option **Öffnen**und dann **Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="d6363-153">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="d6363-154">Wechseln Sie zum folgenden Ordner: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="d6363-154">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span></span>

3. <span data-ttu-id="d6363-155">Wählen Sie **sqlworkflowinstancestoreschemaupgrade. SQL** aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="d6363-155">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>

4. <span data-ttu-id="d6363-156">Wählen Sie den Namen der Persistenzdatenbank in der Dropdown-Option **Verfügbare Datenbanken** aus.</span><span class="sxs-lookup"><span data-stu-id="d6363-156">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>

5. <span data-ttu-id="d6363-157">Wählen Sie im Menü **Abfrage** die Option **Ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="d6363-157">Choose **Execute** from the **Query** menu.</span></span>

<span data-ttu-id="d6363-158">Sobald die Abfrage abgeschlossen ist, wird das Datenbankschema aktualisiert. Sie können jetzt die standardmäßige Workflowidentität anzeigen, die den persistenten Workflowinstanzen zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d6363-158">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="d6363-159">Erweitern Sie die Persistenzdatenbank im Knoten **Datenbanken** des **Objekt-Explorer**, und erweitern Sie dann den Knoten **Sichten** .</span><span class="sxs-lookup"><span data-stu-id="d6363-159">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="d6363-160">Klicken Sie mit der rechten Maustaste auf **System. Activities. DurableInstancing. Instanzen** , und wählen Sie **oberste 1000 Zeilen auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="d6363-160">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="d6363-161">Scrollen Sie zum Ende der Spalten, und beachten Sie, dass der Sicht sechs weitere Spalten hinzugefügt werden: **IdentityName**, **identitypackage**, **Build**, **Major**, **Minor**und **Revision**.</span><span class="sxs-lookup"><span data-stu-id="d6363-161">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="d6363-162">Alle beibehaltenen Workflows weisen für diese Felder den Wert **null** auf, der eine NULL-Workflow Identität darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6363-162">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
