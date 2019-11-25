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
# <a name="using-workflowidentity-and-versioning"></a>Verwenden von WorkflowIdentity und Versionsverwaltung

<xref:System.Activities.WorkflowIdentity> bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Workflowdefinition einen Namen und eine <xref:System.Version> zuzuweisen und diese Informationen einer persistenten Workflowinstanz zuzuordnen. Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates. Dieses Thema bietet eine Übersicht über die Verwendung von <xref:System.Activities.WorkflowIdentity> mit <xref:System.Activities.WorkflowApplication>-Hosting. Informationen zur parallelen Ausführung von Workflow Definitionen in einem Workflow Dienst finden Sie unter parallele [Versionsverwaltung in](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md)Workflow Service Host. Weitere Informationen zum dynamischen Update finden Sie unter [dynamisches Update](dynamic-update.md).

## <a name="in-this-topic"></a>In diesem Thema

- [Verwenden von workflowidentity](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [Parallele Ausführung mithilfe von workflowidentity](using-workflowidentity-and-versioning.md#SxS)

- [Aktualisieren von .NET Framework 4 Persistenzdatenbanken zur Unterstützung der Workflow Versionsverwaltung](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [So aktualisieren Sie das Datenbankschema](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a>Verwenden von workflowidentity

Um <xref:System.Activities.WorkflowIdentity> zu verwenden, erstellen Sie eine Instanz, konfigurieren diese und ordnen sie einer <xref:System.Activities.WorkflowApplication>-Instanz zu. Eine <xref:System.Activities.WorkflowIdentity>-Instanz enthält drei identifizierende Informationen. <xref:System.Activities.WorkflowIdentity.Name%2A> und <xref:System.Activities.WorkflowIdentity.Version%2A> enthalten einen Namen und eine <xref:System.Version> und sind erforderlich. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und kann verwendet werden, um eine zusätzliche Zeichenfolge anzugeben, die Informationen wie den Assemblynamen oder andere gewünschte Informationen enthält. <xref:System.Activities.WorkflowIdentity> ist eindeutig, wenn jede ihrer drei Eigenschaften sich von einer anderen <xref:System.Activities.WorkflowIdentity> unterscheidet.

> [!IMPORTANT]
> <xref:System.Activities.WorkflowIdentity> sollte keine persönlich identifizierbaren Informationen (PII) enthalten. Informationen über die <xref:System.Activities.WorkflowIdentity>-Aktivität, mit der eine Instanz erstellt wird, werden von der Laufzeit zu verschiedenen Zeiten des Aktivitätslebenszyklus an alle konfigurierten Überwachungsdienste ausgegeben. Die WF-Nachverfolgung besitzt keinen Mechanismus, um PII (vertrauliche Benutzerdaten) auszublenden. Daher sollte eine <xref:System.Activities.WorkflowIdentity>-Instanz keine PII-Daten enthalten, die möglicherweise von der Laufzeit in die Überwachungsdatensätze ausgegeben werden und so für jede Person mit Anzeigerechten für Überwachungsdatensätze sichtbar sind.

Im folgenden Beispiel wird <xref:System.Activities.WorkflowIdentity> erstellt und einer Instanz eines Workflows zugeordnet, der mit einer `MortgageWorkflow`-Workflowdefinition erstellt wurde.

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

Beim erneuten Laden und Fortsetzen eines Workflows muss eine <xref:System.Activities.WorkflowIdentity> verwendet werden, die in Übereinstimmung mit der <xref:System.Activities.WorkflowIdentity> der persistenten Workflowinstanz konfiguriert ist.

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

Wenn die beim erneuten Laden der Workflowinstanz verwendete <xref:System.Activities.WorkflowIdentity> nicht mit der persistenten <xref:System.Activities.WorkflowIdentity> übereinstimmt, wird <xref:System.Activities.VersionMismatchException> ausgelöst. Im folgenden Beispiel wird versucht, die `MortgageWorkflow`-Instanz zu laden, die im vorherigen Beispiel persistent gespeichert wurde. Dieser Ladeversuch wird mithilfe einer <xref:System.Activities.WorkflowIdentity> ausgeführt, die für eine neuere Version des Hypothekenworkflows konfiguriert wurde, die nicht der persistenten Instanz entspricht.

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

Beim Ausführen des vorangehenden Codes wird folgende <xref:System.Activities.VersionMismatchException> ausgelöst.

```
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a>Parallele Ausführung mithilfe von workflowidentity

<xref:System.Activities.WorkflowIdentity> kann verwendet werden, um die parallele Ausführung mehrerer Workflowversionen zu erleichtern. Ein häufiges Szenario besteht darin, die Geschäftsanforderungen in einem Workflow mit langer Laufzeit zu ändern. Bei der Bereitstellung einer aktualisierten Version können viele Instanzen eines Workflows ausgeführt werden. Die Hostanwendung kann so konfiguriert werden, dass die aktualisierte Workflowdefinition beim Starten neuer Instanzen verwendet wird, und sie muss dafür sorgen, beim Fortsetzen von Instanzen die richtige Workflowdefinition bereitzustellen. <xref:System.Activities.WorkflowIdentity> kann verwendet werden, um beim Fortsetzen von Workflowinstanzen die entsprechende Workflowdefinition zu identifizieren und bereitzustellen.

Um die <xref:System.Activities.WorkflowIdentity> einer persistenten Workflowinstanz abzurufen, wird die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet. Die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet die <xref:System.Activities.WorkflowApplication.Id%2A> der persistenten Workflowinstanz und den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, der die persistente Instanz enthält und <xref:System.Activities.WorkflowApplicationInstance> zurückgibt. <xref:System.Activities.WorkflowApplicationInstance> enthält Informationen über eine persistente Workflowinstanz, einschließlich der zugeordneten <xref:System.Activities.WorkflowIdentity>. Diese zugeordnete <xref:System.Activities.WorkflowIdentity> kann vom Host verwendet werden, um die richtige Workflowdefinition bereitzustellen, wenn die Workflowinstanz geladen und fortgesetzt wird.

> [!NOTE]
> Eine leere <xref:System.Activities.WorkflowIdentity> ist gültig und kann vom Host verwendet werden, um Instanzen, die ohne zugeordnete <xref:System.Activities.WorkflowIdentity> gespeichert wurden, der richtigen Workflowdefinition zuzuordnen. Dieses Szenario kann auftreten, wenn eine Workflow Anwendung nicht anfänglich mit der Workflow Versionsverwaltung geschrieben wurde oder wenn eine Anwendung von .NET Framework 4 aktualisiert wird. Weitere Informationen finden [Sie unter Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflow Versions](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)Verwaltung.

Im folgenden Beispiel wird eine `Dictionary<WorkflowIdentity, Activity>` verwendet, um <xref:System.Activities.WorkflowIdentity>-Instanzen den entsprechenden Workflow Definitionen zuzuordnen, und ein Workflow wird mit der `MortgageWorkflow` Workflow Definition gestartet, die dem `identityV1` <xref:System.Activities.WorkflowIdentity>zugeordnet ist.

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

Im folgenden Beispiel werden Informationen über die persistente Workflowinstanz aus dem vorherigen Beispiel abgerufen, indem <xref:System.Activities.WorkflowApplication.GetInstance%2A> aufgerufen wird, und die persistenten <xref:System.Activities.WorkflowIdentity>-Informationen werden verwendet, um die entsprechende Workflowdefinition abzurufen. Diese Informationen werden verwendet, um <xref:System.Activities.WorkflowApplication> zu konfigurieren. Der Workflow wird daraufhin geladen. Da die <xref:System.Activities.WorkflowApplication.Load%2A>-Überladung, die <xref:System.Activities.WorkflowApplicationInstance> annimmt, verwendet wird, wird von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> der für <xref:System.Activities.WorkflowApplicationInstance> konfigurierte <xref:System.Activities.WorkflowApplication> verwendet, sodass die zugehörige <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft nicht konfiguriert werden muss.

> [!NOTE]
> Wenn die <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft festgelegt wird, muss sie mit derselben <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Instanz festgelegt werden, die von <xref:System.Activities.WorkflowApplicationInstance> verwendet wird, da andernfalls <xref:System.ArgumentException> mit der folgenden Meldung ausgelöst wird: `The instance is configured with a different InstanceStore than this WorkflowApplication.`

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

## <a name="UpdatingWF4PersistenceDatabases"></a>Aktualisieren von .NET Framework 4 Persistenzdatenbanken zur Unterstützung der Workflow Versionsverwaltung

Ein sqlworkflowinstancestoreschemaupgrade. SQL-Datenbankskript wird zur Aktualisierung von Persistenzdatenbanken bereitgestellt, die mit den .NET Framework 4-Daten Bank Skripts erstellt Dieses Skript aktualisiert die Datenbanken, um die neuen Versions Verwaltungsfunktionen zu unterstützen, die in .NET Framework 4,5 eingeführt wurden. Den persistenten Workflowinstanzen in den Datenbanken werden Standardversionswerte zugeordnet, und sie können an einer parallelen Ausführung und an dynamischen Updates beteiligt sein.

Wenn eine .NET Framework 4,5-Workflow Anwendung alle Persistenzvorgänge versucht, die die neuen Versions Verwaltungsfunktionen für eine Persistenzdatenbank verwenden, die nicht mit dem bereitgestellten Skript aktualisiert wurde, wird eine-<xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> mit einer Meldung ausgelöst, die der folgenden Meldung ähnelt:

```
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a>So aktualisieren Sie das Datenbankschema

1. Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit dem persistenzdatenbankserver her, z.b. **.\sqlexpress**

2. Wählen Sie im Menü **Datei** die Option **Öffnen**und dann **Datei** aus. Wechseln Sie zum folgenden Ordner: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`

3. Wählen Sie **sqlworkflowinstancestoreschemaupgrade. SQL** aus, und klicken Sie auf **Öffnen**.

4. Wählen Sie den Namen der Persistenzdatenbank in der Dropdown-Option **Verfügbare Datenbanken** aus.

5. Wählen Sie im Menü **Abfrage** die Option **Ausführen** aus.

Sobald die Abfrage abgeschlossen ist, wird das Datenbankschema aktualisiert. Sie können jetzt die standardmäßige Workflowidentität anzeigen, die den persistenten Workflowinstanzen zugewiesen wurde. Erweitern Sie die Persistenzdatenbank im Knoten **Datenbanken** des **Objekt-Explorer**, und erweitern Sie dann den Knoten **Sichten** . Klicken Sie mit der rechten Maustaste auf **System. Activities. DurableInstancing. Instanzen** , und wählen Sie **oberste 1000 Zeilen auswählen**aus. Scrollen Sie zum Ende der Spalten, und beachten Sie, dass der Sicht sechs weitere Spalten hinzugefügt werden: **IdentityName**, **identitypackage**, **Build**, **Major**, **Minor**und **Revision**. Alle beibehaltenen Workflows weisen für diese Felder den Wert **null** auf, der eine NULL-Workflow Identität darstellt.
