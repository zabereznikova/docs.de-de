---
title: Dynamisches Update
ms.date: 03/30/2017
ms.assetid: 8b6ef19b-9691-4b4b-824c-3c651a9db96e
ms.openlocfilehash: cb4b63a67aa6e9033b227198e2ecc2b1b80db927
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190155"
---
# <a name="dynamic-update"></a><span data-ttu-id="8454f-102">Dynamisches Update</span><span class="sxs-lookup"><span data-stu-id="8454f-102">Dynamic Update</span></span>

<span data-ttu-id="8454f-103">Dynamische Updates bieten Entwicklern von Workflowanwendungen die Möglichkeit, die Workflowdefinition einer persistenten Workflowinstanz zu aktualisieren,</span><span class="sxs-lookup"><span data-stu-id="8454f-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="8454f-104">beispielsweise um eine Fehlerkorrektur oder neue Anforderungen zu implementieren oder um unerwartete Änderungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="8454f-104">This can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="8454f-105">Dieses Thema enthält eine Übersicht über die Funktionen des dynamischen Updates, die in .NET Framework 4,5 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="8454f-105">This topic provides an overview of the dynamic update functionality introduced in .NET Framework 4.5.</span></span>

## <a name="dynamic-update"></a><span data-ttu-id="8454f-106">Dynamisches Update</span><span class="sxs-lookup"><span data-stu-id="8454f-106">Dynamic Update</span></span>

<span data-ttu-id="8454f-107">Um dynamische Updates auf eine persistente Workflowinstanz anzuwenden, wird eine <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> mit Anweisungen für die Laufzeit erstellt, die beschreiben, wie die persistente Workflowinstanz in Anpassung an die gewünschten Änderungen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8454f-107">To apply dynamic updates to a persisted workflow instance, a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> is created that contains instructions for the runtime that describe how to modify the persisted workflow instance to reflect the desired changes.</span></span> <span data-ttu-id="8454f-108">Nachdem die Updatezuordnung erstellt wurde, wird sie auf die gewünschten persistenten Workflowinstanzen angewendet.</span><span class="sxs-lookup"><span data-stu-id="8454f-108">Once the update map is created, it is applied to the desired persisted workflow instances.</span></span> <span data-ttu-id="8454f-109">Nachdem das dynamische Update angewendet wurde, kann die Workflowinstanz mithilfe der neuen aktualisierten Workflowdefinition fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8454f-109">Once the dynamic update is applied, the workflow instance may be resumed using the new updated workflow definition.</span></span> <span data-ttu-id="8454f-110">Es gibt vier Schritte, die beim Erstellen und Anwenden einer Updatezuordnung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8454f-110">There are four steps required to create and apply an update map.</span></span>

1. [<span data-ttu-id="8454f-111">Vorbereiten der Workflowdefinition für ein dynamisches Update</span><span class="sxs-lookup"><span data-stu-id="8454f-111">Prepare the workflow definition for dynamic update</span></span>](dynamic-update.md#Prepare)

2. [<span data-ttu-id="8454f-112">Aktualisieren der Workflowdefinition, um die gewünschten Änderungen widerzuspiegeln</span><span class="sxs-lookup"><span data-stu-id="8454f-112">Update the workflow definition to reflect the desired changes</span></span>](dynamic-update.md#Update)

3. [<span data-ttu-id="8454f-113">Erstellen der Updatezuordnung</span><span class="sxs-lookup"><span data-stu-id="8454f-113">Create the update map</span></span>](dynamic-update.md#Create)

4. [<span data-ttu-id="8454f-114">Anwenden der Updatezuordnung auf die gewünschten persistenten Workflowinstanzen</span><span class="sxs-lookup"><span data-stu-id="8454f-114">Apply the update map to the desired persisted workflow instances</span></span>](dynamic-update.md#Apply)

> [!NOTE]
> <span data-ttu-id="8454f-115">Beachten Sie, dass die Schritte 1 bis 3, die die Erstellung der Updatezuordnung umfassen, unabhängig davon ausgeführt werden können, ob das Update angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8454f-115">Note that steps 1 through 3, which cover the creation of the update map, may be performed independently of applying the update.</span></span> <span data-ttu-id="8454f-116">Ein häufiges Szenario, in dem der Workflow Entwickler die Update Zuordnung offline erstellt, und dann wird das Update von einem Administrator zu einem späteren Zeitpunkt angewendet.</span><span class="sxs-lookup"><span data-stu-id="8454f-116">A common scenario that the workflow developer will create the update map offline, and then an administrator will apply the update at a later time.</span></span>

<span data-ttu-id="8454f-117">Dieses Thema bietet eine Übersicht über den dynamischen Updateprozess, in dem einer persistenten Instanz eines kompilierten XAML-Workflows eine neue Aktivität hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8454f-117">This topic provides an overview of the dynamic update process of adding a new activity to a persisted instance of a compiled Xaml workflow.</span></span>

### <a name="prepare-the-workflow-definition-for-dynamic-update"></a><a name="Prepare"></a> <span data-ttu-id="8454f-118">Vorbereiten der Workflow Definition für das dynamische Update</span><span class="sxs-lookup"><span data-stu-id="8454f-118">Prepare the workflow definition for dynamic update</span></span>

<span data-ttu-id="8454f-119">Der erste Schritt im dynamischen Updateprozess besteht darin, die gewünschte Workflowdefinition für das Update vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="8454f-119">The first step in the dynamic update process is to prepare the desired workflow definition for update.</span></span> <span data-ttu-id="8454f-120">Hierzu wird die <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>-Methode aufgerufen und die zu ändernde Workflowdefinition übergeben.</span><span class="sxs-lookup"><span data-stu-id="8454f-120">This is done by calling the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method and passing in the workflow definition to modify.</span></span> <span data-ttu-id="8454f-121">Diese Methode überprüft und durchläuft die Workflowstruktur, um alle Objekte, wie öffentliche Aktivitäten und Variablen, zu identifizieren, die gekennzeichnet werden müssen, damit sie später mit der geänderten Workflowdefinition verglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="8454f-121">This method validates and then walks the workflow tree to identify all of the objects such as public activities and variables that need to be tagged so they can be compared later with the modified workflow definition.</span></span> <span data-ttu-id="8454f-122">Danach wird die Workflowstruktur geklont und an die ursprüngliche Workflowdefinition angefügt.</span><span class="sxs-lookup"><span data-stu-id="8454f-122">When this is complete, the workflow tree is cloned and attached to the original workflow definition.</span></span> <span data-ttu-id="8454f-123">Wenn die Updatezuordnung erstellt wird, wird die aktualisierte Version der Workflowdefinition mit der ursprünglichen Workflowdefinition verglichen und die Updatezuordnung auf Grundlage der Unterschiede generiert.</span><span class="sxs-lookup"><span data-stu-id="8454f-123">When the update map is created, the updated version of the workflow definition is compared with the original workflow definition and the update map is generated based on the differences.</span></span>

<span data-ttu-id="8454f-124">Um einen XAML-Workflow für ein dynamisches Update vorzubereiten, kann er in <xref:System.Activities.ActivityBuilder> geladen werden, und anschließend wird <xref:System.Activities.ActivityBuilder> an <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> übergeben.</span><span class="sxs-lookup"><span data-stu-id="8454f-124">To prepare a Xaml workflow for dynamic update it may be loaded into an <xref:System.Activities.ActivityBuilder>, and then the <xref:System.Activities.ActivityBuilder> is passed into <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="8454f-125">Weitere Informationen zum Arbeiten mit serialisierten Workflows und <xref:System.Activities.ActivityBuilder> finden Sie unter [Serialisieren von Workflows und Aktivitäten in und aus XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="8454f-125">For more information about working with serialized workflows and <xref:System.Activities.ActivityBuilder>, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

<span data-ttu-id="8454f-126">Im folgenden Beispiel wird eine `MortgageWorkflow`-Definition (die aus <xref:System.Activities.Statements.Sequence> mit mehreren untergeordneten Aktivitäten besteht) in <xref:System.Activities.ActivityBuilder> geladen und anschließend für das dynamische Update vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="8454f-126">In the following example, a `MortgageWorkflow` definition (that consists of a <xref:System.Activities.Statements.Sequence> with several child activities) is loaded into an <xref:System.Activities.ActivityBuilder>, and then prepared for dynamic update.</span></span> <span data-ttu-id="8454f-127">Nach der Methodenrückgabe enthält <xref:System.Activities.ActivityBuilder> die ursprüngliche Workflowdefinition sowie eine Kopie.</span><span class="sxs-lookup"><span data-stu-id="8454f-127">After the method returns, the <xref:System.Activities.ActivityBuilder> contains the original workflow definition as well as a copy.</span></span>

```csharp
// Load the MortgageWorkflow definition from Xaml into
// an ActivityBuilder.
XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
{
    LocalAssembly = Assembly.GetExecutingAssembly()
};

XamlXmlReader xamlReader = new XamlXmlReader(@"C:\WorkflowDefinitions\MortgageWorkflow.xaml",
    readerSettings);

ActivityBuilder ab = XamlServices.Load(
    ActivityXamlServices.CreateBuilderReader(xamlReader)) as ActivityBuilder;

// Prepare the workflow definition for dynamic update.
DynamicUpdateServices.PrepareForUpdate(ab);
```

### <a name="update-the-workflow-definition-to-reflect-the-desired-changes"></a><a name="Update"></a> <span data-ttu-id="8454f-128">Aktualisieren der Workflow Definition, um die gewünschten Änderungen widerzuspiegeln</span><span class="sxs-lookup"><span data-stu-id="8454f-128">Update the workflow definition to reflect the desired changes</span></span>

<span data-ttu-id="8454f-129">Sobald die Workflowdefinition für das Update vorbereitet wurde, können die gewünschten Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="8454f-129">Once the workflow definition has been prepared for updating, the desired changes can be made.</span></span> <span data-ttu-id="8454f-130">Sie können Aktivitäten hinzufügen oder entfernen, öffentliche Variablen hinzufügen, verschieben oder löschen, Argumente hinzufügen oder entfernen und Änderungen an der Signatur von Aktivitätsdelegaten vornehmen.</span><span class="sxs-lookup"><span data-stu-id="8454f-130">You can add or remove activities, add, move or delete public variables, add or remove arguments, and make changes to the signature of activity delegates.</span></span> <span data-ttu-id="8454f-131">Es ist nicht möglich, eine ausgeführte Aktivität zu entfernen oder die Signatur eines ausgeführten Delegaten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8454f-131">You cannot remove a running activity or change the signature of a running delegate.</span></span> <span data-ttu-id="8454f-132">Diese Änderungen können mithilfe von Code oder in einem neu gehosteten Workflow-Designer vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="8454f-132">These changes may be made using code, or in a re-hosted workflow designer.</span></span> <span data-ttu-id="8454f-133">Im folgenden Beispiel wird eine benutzerdefinierte `VerifyAppraisal`-Aktivität der Sequence-Aktivität hinzugefügt, die den Text von `MortgageWorkflow` aus dem vorherigen Beispiel darstellt.</span><span class="sxs-lookup"><span data-stu-id="8454f-133">In the following example, a custom `VerifyAppraisal` activity is added to the Sequence that makes up the body of the `MortgageWorkflow` from the previous example.</span></span>

```csharp
// Make desired changes to the definition. In this example, we are
// inserting a new VerifyAppraisal activity as the 3rd child of the root Sequence.
VerifyAppraisal va = new VerifyAppraisal
{
    Result = new VisualBasicReference<bool>("LoanCriteria")
};

// Get the Sequence that makes up the body of the workflow.
Sequence s = ab.Implementation as Sequence;

// Insert the new activity into the Sequence.
s.Activities.Insert(2, va);
```

### <a name="create-the-update-map"></a><a name="Create"></a> <span data-ttu-id="8454f-134">Erstellen der Update Zuordnung</span><span class="sxs-lookup"><span data-stu-id="8454f-134">Create the update map</span></span>

<span data-ttu-id="8454f-135">Sobald die Workflowdefinition, die für das Update vorbereitet wurde, geändert wurde, kann die Updatezuordnung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8454f-135">Once the workflow definition that was prepared for update has been modified, the update map can be created.</span></span> <span data-ttu-id="8454f-136">Um eine dynamische Updatezuordnung zu erstellen, wird die <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8454f-136">To create a dynamic update map, the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> method is invoked.</span></span> <span data-ttu-id="8454f-137">Dadurch wird <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> mit den Informationen zurückgegeben, die die Laufzeit benötigt, um eine persistente Workflowinstanz zu ändern, damit sie geladen und mit der neuen Workflowdefinition fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8454f-137">This returns a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> that contains the information the runtime needs to modify a persisted workflow instance so that it may be loaded and resumed with the new workflow definition.</span></span> <span data-ttu-id="8454f-138">Im folgenden Beispiel wird eine dynamische Zuordnung für die geänderte `MortgageWorkflow` Definition aus dem vorherigen Beispiel erstellt.</span><span class="sxs-lookup"><span data-stu-id="8454f-138">In the following example, a dynamic map is created for the modified `MortgageWorkflow` definition from the previous example.</span></span>

```csharp
// Create the update map.
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);
```

<span data-ttu-id="8454f-139">Diese Updatezuordnung kann sofort verwendet werden, um persistente Workflowinstanzen zu ändern. Meistens wird sie jedoch gespeichert, und die Updates werden später angewendet.</span><span class="sxs-lookup"><span data-stu-id="8454f-139">This update map can immediately be used to modify persisted workflow instances, or more typically it can be saved and the updates applied later.</span></span> <span data-ttu-id="8454f-140">Eine Möglichkeit zum Speichern der Updatezuordnung besteht darin, sie in eine Datei zu serialisieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8454f-140">One way to save the update map is to serialize it to a file, as shown in the following example.</span></span>

```csharp
// Serialize the update map to a file.
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefinitions\MortgageWorkflow.map", FileMode.Create))
{
    serializer.WriteObject(fs, map);
}
```

<span data-ttu-id="8454f-141">Wenn <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> zurückgegeben wird, werden die geklonte Workflowdefinition und andere Informationen zum dynamischen Update, die im Aufruf von <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> hinzugefügt wurden, entfernt. Die geänderte Workflowdefinition kann jetzt gespeichert werden, sodass sie später beim Fortsetzen aktualisierter Workflowinstanzen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8454f-141">When <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> returns, the cloned workflow definition and other dynamic update information that was added in the call to <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> is removed, and the modified workflow definition is ready to be saved so that it can be used later when resuming updated workflow instances.</span></span> <span data-ttu-id="8454f-142">Im folgenden Beispiel wird die geänderte Workflowdefinition in `MortgageWorkflow_v1.1.xaml` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8454f-142">In the following example, the modified workflow definition is saved to `MortgageWorkflow_v1.1.xaml`.</span></span>

```csharp
// Save the modified workflow definition.
StreamWriter sw = File.CreateText(@"C:\WorkflowDefinitions\MortgageWorkflow_v1.1.xaml");
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
sw.Close();
```

### <a name="apply-the-update-map-to-the-desired-persisted-workflow-instances"></a><a name="Apply"></a> <span data-ttu-id="8454f-143">Anwenden der Update Zuordnung auf die gewünschten persistenten Workflow Instanzen</span><span class="sxs-lookup"><span data-stu-id="8454f-143">Apply the update map to the desired persisted workflow instances</span></span>

<span data-ttu-id="8454f-144">Die Updatezuordnung kann jederzeit angewendet werden, nachdem sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8454f-144">Applying the update map can be done at any time after creating it.</span></span> <span data-ttu-id="8454f-145">Sie kann mithilfe der <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>-Instanz, die von <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> zurückgegeben wurde, direkt ausgeführt werden, oder später mithilfe einer gespeicherten Kopie der Updatezuordnung.</span><span class="sxs-lookup"><span data-stu-id="8454f-145">It can be done right away using the <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> instance that was returned by <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, or it can be done later using a saved copy of the update map.</span></span> <span data-ttu-id="8454f-146">Um eine Workflowinstanz zu aktualisieren, laden Sie sie unter Verwendung von <xref:System.Activities.WorkflowApplicationInstance> in <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8454f-146">To update a workflow instance, load it into a <xref:System.Activities.WorkflowApplicationInstance> using <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8454f-147">Als Nächstes erstellen Sie <xref:System.Activities.WorkflowApplication> mithilfe der aktualisierten Workflowdefinition und unter Verwendung der gewünschten <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="8454f-147">Next, create a <xref:System.Activities.WorkflowApplication> using the updated workflow definition, and the desired <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="8454f-148"><xref:System.Activities.WorkflowIdentity> kann sich von der Identität unterscheiden, die zum persistenten Speichern des ursprünglichen Workflows verwendet wurde. Sie wird in der Regel verwendet, um anzugeben, dass die persistente Instanz geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="8454f-148">This <xref:System.Activities.WorkflowIdentity> may be different than the one that was used to persist the original workflow, and typically is in order to reflect that the persisted instance has been modified.</span></span> <span data-ttu-id="8454f-149">Nachdem<xref:System.Activities.WorkflowApplication> erstellt wurde, wird sie mithilfe der Überladung von <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType>, das <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> verwendet, geladen und dann mit einem Aufruf von <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType> entladen.</span><span class="sxs-lookup"><span data-stu-id="8454f-149">Once the <xref:System.Activities.WorkflowApplication> is created, it is loaded using the overload of <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> that takes a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>, and then unloaded with a call to <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8454f-150">Dadurch wird das dynamische Update angewendet und die aktualisierte Workflowinstanz persistent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8454f-150">This applies the dynamic update and persists the updated workflow instance.</span></span>

```csharp
// Load the serialized update map.
DynamicUpdateMap map;
using (FileStream fs = File.Open(@"C:\WorkflowDefinitions\MortgageWorkflow.map", FileMode.Open))
{
    DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
    object updateMap = serializer.ReadObject(fs);
    if (updateMap == null)
    {
        throw new ApplicationException("DynamicUpdateMap is null.");
    }

    map = (DynamicUpdateMap)updateMap;
}

// Retrieve a list of workflow instance ids that corresponds to the
// workflow instances to update. This step is the responsibility of
// the application developer.
List<Guid> ids = GetPersistedWorkflowIds();
foreach (Guid id in ids)
{
    // Get a proxy to the persisted workflow instance.
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(id, store);

    // If desired, you can inspect the WorkflowIdentity of the instance
    // using the DefinitionIdentity property to determine whether to apply
    // the update.
    Console.WriteLine(instance.DefinitionIdentity);

    // Create a workflow application. You must specify the updated workflow definition, and
    // you may provide an updated WorkflowIdentity if desired to reflect the update.
    WorkflowIdentity identity = new WorkflowIdentity
    {
        Name = "MortgageWorkflow v1.1",
        Version = new Version(1, 1, 0, 0)
    };

    // Load the persisted workflow instance using the updated workflow definition
    // and with an updated WorkflowIdentity. In this example the MortgageWorkflow class
    // contains the updated definition.
    WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

    // Apply the dynamic update on the loaded instance.
    wfApp.Load(instance, map);

    // Unload the updated instance.
    wfApp.Unload();
}
```

### <a name="resuming-an-updated-workflow-instance"></a><span data-ttu-id="8454f-151">Fortsetzen einer aktualisierten Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="8454f-151">Resuming an Updated Workflow Instance</span></span>

<span data-ttu-id="8454f-152">Nachdem ein dynamisches Update angewendet wurde, kann die Workflowinstanz fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8454f-152">Once dynamic update has been applied, the workflow instance may be resumed.</span></span> <span data-ttu-id="8454f-153">Beachten Sie, dass die neue aktualisierte Definition und <xref:System.Activities.WorkflowIdentity> verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8454f-153">Note that the new updated definition and <xref:System.Activities.WorkflowIdentity> must be used.</span></span>

> [!NOTE]
> <span data-ttu-id="8454f-154">Weitere Informationen zum Arbeiten mit <xref:System.Activities.WorkflowApplication> und <xref:System.Activities.WorkflowIdentity> finden Sie unter [Verwenden von workflowidentity und Versions](using-workflowidentity-and-versioning.md)Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="8454f-154">For more information about working with <xref:System.Activities.WorkflowApplication> and <xref:System.Activities.WorkflowIdentity>, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

<span data-ttu-id="8454f-155">Im folgenden Beispiel wurde der `MortgageWorkflow_v1.1.xaml`-Workflow aus dem vorherigen Beispiel kompiliert. Anschließend wird er geladen und mit der aktualisierten Workflowdefinition fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8454f-155">In the following example, the `MortgageWorkflow_v1.1.xaml` workflow from the previous example has been compiled, and is loaded and resumed using the updated workflow definition.</span></span>

```csharp
// Load the persisted workflow instance using the updated workflow definition
// and updated WorkflowIdentity.
WorkflowIdentity identity = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1.1",
    Version = new Version(1, 1, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure persistence and desired workflow event handlers.
// (Omitted for brevity.)
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(InstanceId);

// Resume the workflow.
// wfApp.ResumeBookmark(...);
```
