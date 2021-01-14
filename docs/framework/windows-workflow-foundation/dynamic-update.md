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
# <a name="dynamic-update"></a>Dynamisches Update

Dynamische Updates bieten Entwicklern von Workflowanwendungen die Möglichkeit, die Workflowdefinition einer persistenten Workflowinstanz zu aktualisieren, beispielsweise um eine Fehlerkorrektur oder neue Anforderungen zu implementieren oder um unerwartete Änderungen zu berücksichtigen. Dieses Thema enthält eine Übersicht über die Funktionen des dynamischen Updates, die in .NET Framework 4,5 eingeführt wurden.

## <a name="dynamic-update"></a>Dynamisches Update

Um dynamische Updates auf eine persistente Workflowinstanz anzuwenden, wird eine <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> mit Anweisungen für die Laufzeit erstellt, die beschreiben, wie die persistente Workflowinstanz in Anpassung an die gewünschten Änderungen geändert wird. Nachdem die Updatezuordnung erstellt wurde, wird sie auf die gewünschten persistenten Workflowinstanzen angewendet. Nachdem das dynamische Update angewendet wurde, kann die Workflowinstanz mithilfe der neuen aktualisierten Workflowdefinition fortgesetzt werden. Es gibt vier Schritte, die beim Erstellen und Anwenden einer Updatezuordnung erforderlich sind.

1. [Vorbereiten der Workflowdefinition für ein dynamisches Update](dynamic-update.md#Prepare)

2. [Aktualisieren der Workflowdefinition, um die gewünschten Änderungen widerzuspiegeln](dynamic-update.md#Update)

3. [Erstellen der Updatezuordnung](dynamic-update.md#Create)

4. [Anwenden der Updatezuordnung auf die gewünschten persistenten Workflowinstanzen](dynamic-update.md#Apply)

> [!NOTE]
> Beachten Sie, dass die Schritte 1 bis 3, die die Erstellung der Updatezuordnung umfassen, unabhängig davon ausgeführt werden können, ob das Update angewendet wird. Ein häufiges Szenario, in dem der Workflow Entwickler die Update Zuordnung offline erstellt, und dann wird das Update von einem Administrator zu einem späteren Zeitpunkt angewendet.

Dieses Thema bietet eine Übersicht über den dynamischen Updateprozess, in dem einer persistenten Instanz eines kompilierten XAML-Workflows eine neue Aktivität hinzugefügt wird.

### <a name="prepare-the-workflow-definition-for-dynamic-update"></a><a name="Prepare"></a> Vorbereiten der Workflow Definition für das dynamische Update

Der erste Schritt im dynamischen Updateprozess besteht darin, die gewünschte Workflowdefinition für das Update vorzubereiten. Hierzu wird die <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>-Methode aufgerufen und die zu ändernde Workflowdefinition übergeben. Diese Methode überprüft und durchläuft die Workflowstruktur, um alle Objekte, wie öffentliche Aktivitäten und Variablen, zu identifizieren, die gekennzeichnet werden müssen, damit sie später mit der geänderten Workflowdefinition verglichen werden können. Danach wird die Workflowstruktur geklont und an die ursprüngliche Workflowdefinition angefügt. Wenn die Updatezuordnung erstellt wird, wird die aktualisierte Version der Workflowdefinition mit der ursprünglichen Workflowdefinition verglichen und die Updatezuordnung auf Grundlage der Unterschiede generiert.

Um einen XAML-Workflow für ein dynamisches Update vorzubereiten, kann er in <xref:System.Activities.ActivityBuilder> geladen werden, und anschließend wird <xref:System.Activities.ActivityBuilder> an <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> übergeben.

> [!NOTE]
> Weitere Informationen zum Arbeiten mit serialisierten Workflows und <xref:System.Activities.ActivityBuilder> finden Sie unter [Serialisieren von Workflows und Aktivitäten in und aus XAML](serializing-workflows-and-activities-to-and-from-xaml.md).

Im folgenden Beispiel wird eine `MortgageWorkflow`-Definition (die aus <xref:System.Activities.Statements.Sequence> mit mehreren untergeordneten Aktivitäten besteht) in <xref:System.Activities.ActivityBuilder> geladen und anschließend für das dynamische Update vorbereitet. Nach der Methodenrückgabe enthält <xref:System.Activities.ActivityBuilder> die ursprüngliche Workflowdefinition sowie eine Kopie.

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

### <a name="update-the-workflow-definition-to-reflect-the-desired-changes"></a><a name="Update"></a> Aktualisieren der Workflow Definition, um die gewünschten Änderungen widerzuspiegeln

Sobald die Workflowdefinition für das Update vorbereitet wurde, können die gewünschten Änderungen vorgenommen werden. Sie können Aktivitäten hinzufügen oder entfernen, öffentliche Variablen hinzufügen, verschieben oder löschen, Argumente hinzufügen oder entfernen und Änderungen an der Signatur von Aktivitätsdelegaten vornehmen. Es ist nicht möglich, eine ausgeführte Aktivität zu entfernen oder die Signatur eines ausgeführten Delegaten zu ändern. Diese Änderungen können mithilfe von Code oder in einem neu gehosteten Workflow-Designer vorgenommen werden. Im folgenden Beispiel wird eine benutzerdefinierte `VerifyAppraisal`-Aktivität der Sequence-Aktivität hinzugefügt, die den Text von `MortgageWorkflow` aus dem vorherigen Beispiel darstellt.

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

### <a name="create-the-update-map"></a><a name="Create"></a> Erstellen der Update Zuordnung

Sobald die Workflowdefinition, die für das Update vorbereitet wurde, geändert wurde, kann die Updatezuordnung erstellt werden. Um eine dynamische Updatezuordnung zu erstellen, wird die <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>-Methode aufgerufen. Dadurch wird <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> mit den Informationen zurückgegeben, die die Laufzeit benötigt, um eine persistente Workflowinstanz zu ändern, damit sie geladen und mit der neuen Workflowdefinition fortgesetzt werden kann. Im folgenden Beispiel wird eine dynamische Zuordnung für die geänderte `MortgageWorkflow` Definition aus dem vorherigen Beispiel erstellt.

```csharp
// Create the update map.
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);
```

Diese Updatezuordnung kann sofort verwendet werden, um persistente Workflowinstanzen zu ändern. Meistens wird sie jedoch gespeichert, und die Updates werden später angewendet. Eine Möglichkeit zum Speichern der Updatezuordnung besteht darin, sie in eine Datei zu serialisieren, wie im folgenden Beispiel gezeigt.

```csharp
// Serialize the update map to a file.
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefinitions\MortgageWorkflow.map", FileMode.Create))
{
    serializer.WriteObject(fs, map);
}
```

Wenn <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> zurückgegeben wird, werden die geklonte Workflowdefinition und andere Informationen zum dynamischen Update, die im Aufruf von <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> hinzugefügt wurden, entfernt. Die geänderte Workflowdefinition kann jetzt gespeichert werden, sodass sie später beim Fortsetzen aktualisierter Workflowinstanzen verwendet werden kann. Im folgenden Beispiel wird die geänderte Workflowdefinition in `MortgageWorkflow_v1.1.xaml` gespeichert.

```csharp
// Save the modified workflow definition.
StreamWriter sw = File.CreateText(@"C:\WorkflowDefinitions\MortgageWorkflow_v1.1.xaml");
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
sw.Close();
```

### <a name="apply-the-update-map-to-the-desired-persisted-workflow-instances"></a><a name="Apply"></a> Anwenden der Update Zuordnung auf die gewünschten persistenten Workflow Instanzen

Die Updatezuordnung kann jederzeit angewendet werden, nachdem sie erstellt wurde. Sie kann mithilfe der <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>-Instanz, die von <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> zurückgegeben wurde, direkt ausgeführt werden, oder später mithilfe einer gespeicherten Kopie der Updatezuordnung. Um eine Workflowinstanz zu aktualisieren, laden Sie sie unter Verwendung von <xref:System.Activities.WorkflowApplicationInstance> in <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>. Als Nächstes erstellen Sie <xref:System.Activities.WorkflowApplication> mithilfe der aktualisierten Workflowdefinition und unter Verwendung der gewünschten <xref:System.Activities.WorkflowIdentity>. <xref:System.Activities.WorkflowIdentity> kann sich von der Identität unterscheiden, die zum persistenten Speichern des ursprünglichen Workflows verwendet wurde. Sie wird in der Regel verwendet, um anzugeben, dass die persistente Instanz geändert wurde. Nachdem<xref:System.Activities.WorkflowApplication> erstellt wurde, wird sie mithilfe der Überladung von <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType>, das <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> verwendet, geladen und dann mit einem Aufruf von <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType> entladen. Dadurch wird das dynamische Update angewendet und die aktualisierte Workflowinstanz persistent gespeichert.

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

### <a name="resuming-an-updated-workflow-instance"></a>Fortsetzen einer aktualisierten Workflowinstanz

Nachdem ein dynamisches Update angewendet wurde, kann die Workflowinstanz fortgesetzt werden. Beachten Sie, dass die neue aktualisierte Definition und <xref:System.Activities.WorkflowIdentity> verwendet werden müssen.

> [!NOTE]
> Weitere Informationen zum Arbeiten mit <xref:System.Activities.WorkflowApplication> und <xref:System.Activities.WorkflowIdentity> finden Sie unter [Verwenden von workflowidentity und Versions](using-workflowidentity-and-versioning.md)Verwaltung.

Im folgenden Beispiel wurde der `MortgageWorkflow_v1.1.xaml`-Workflow aus dem vorherigen Beispiel kompiliert. Anschließend wird er geladen und mit der aktualisierten Workflowdefinition fortgesetzt.

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
