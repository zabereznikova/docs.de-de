---
title: Verwenden von WorkflowIdentity und Versionsverwaltung
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 5bed526a47b802c60aa679e53c84af4e14656675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327489"
---
# <a name="using-workflowidentity-and-versioning"></a>Verwenden von WorkflowIdentity und Versionsverwaltung
<xref:System.Activities.WorkflowIdentity> bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Workflowdefinition einen Namen und eine <xref:System.Version> zuzuweisen und diese Informationen einer persistenten Workflowinstanz zuzuordnen. Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates. Dieses Thema bietet eine Übersicht über die Verwendung von <xref:System.Activities.WorkflowIdentity> mit <xref:System.Activities.WorkflowApplication>-Hosting. Weitere Informationen zur Seite-an-Seite-Ausführung von workflowdefinitionen in einem Workflowdienst, finden Sie unter [parallele Versionsverwaltung in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md). Weitere Informationen zu dynamischen Updates finden Sie unter [dynamische Updates](dynamic-update.md).  
  
## <a name="in-this-topic"></a>In diesem Thema  
  
-   [Verwenden von WorkflowIdentity](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)  
  
    -   [Seite-an-Seite-Ausführung mit WorkflowIdentity](using-workflowidentity-and-versioning.md#SxS)  
  
-   [Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflowversionsverwaltung](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)  
  
    -   [Das Datenbankschema aktualisieren.](using-workflowidentity-and-versioning.md#ToUpgrade)  
  
## <a name="UsingWorkflowIdentity"></a> Verwenden von WorkflowIdentity  
 Um <xref:System.Activities.WorkflowIdentity> zu verwenden, erstellen Sie eine Instanz, konfigurieren diese und ordnen sie einer <xref:System.Activities.WorkflowApplication>-Instanz zu. Eine <xref:System.Activities.WorkflowIdentity>-Instanz enthält drei identifizierende Informationen. <xref:System.Activities.WorkflowIdentity.Name%2A> und <xref:System.Activities.WorkflowIdentity.Version%2A> enthalten einen Namen und eine <xref:System.Version> und sind erforderlich. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und kann verwendet werden, um eine zusätzliche Zeichenfolge anzugeben, die Informationen wie den Assemblynamen oder andere gewünschte Informationen enthält. <xref:System.Activities.WorkflowIdentity> ist eindeutig, wenn jede ihrer drei Eigenschaften sich von einer anderen <xref:System.Activities.WorkflowIdentity> unterscheidet.  
  
> [!IMPORTANT]
>  <xref:System.Activities.WorkflowIdentity> sollte keine persönlich identifizierbaren Informationen (PII) enthalten. Informationen über die <xref:System.Activities.WorkflowIdentity>-Aktivität, mit der eine Instanz erstellt wird, werden von der Laufzeit zu verschiedenen Zeiten des Aktivitätslebenszyklus an alle konfigurierten Überwachungsdienste ausgegeben. Die WF-Nachverfolgung besitzt keinen Mechanismus, um PII (vertrauliche Benutzerdaten) auszublenden. Daher sollte eine <xref:System.Activities.WorkflowIdentity>-Instanz keine PII-Daten enthalten, die möglicherweise von der Laufzeit in die Überwachungsdatensätze ausgegeben werden und so für jede Person mit Anzeigerechten für Überwachungsdatensätze sichtbar sind.  
  
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
  
 **Die WorkflowIdentity ('MortgageWorkflow v1; Version = 1.0.0.0') der geladenen Instanz stimmt nicht mit der WorkflowIdentity ('MortgageWorkflow v2; Version = 2.0.0.0') der bereitgestellten Workflowdefinition überein. Die Instanz mit einer anderen Definition geladen werden, oder mit dynamischen Updates aktualisiert.**  
### <a name="SxS"></a> Seite-an-Seite-Ausführung mit WorkflowIdentity  
 <xref:System.Activities.WorkflowIdentity> kann verwendet werden, um die parallele Ausführung mehrerer Workflowversionen zu erleichtern. Ein häufiges Szenario besteht darin, die Geschäftsanforderungen in einem Workflow mit langer Laufzeit zu ändern. Bei der Bereitstellung einer aktualisierten Version können viele Instanzen eines Workflows ausgeführt werden. Die Hostanwendung kann so konfiguriert werden, dass die aktualisierte Workflowdefinition beim Starten neuer Instanzen verwendet wird, und sie muss dafür sorgen, beim Fortsetzen von Instanzen die richtige Workflowdefinition bereitzustellen. <xref:System.Activities.WorkflowIdentity> kann verwendet werden, um beim Fortsetzen von Workflowinstanzen die entsprechende Workflowdefinition zu identifizieren und bereitzustellen.  
  
 Um die <xref:System.Activities.WorkflowIdentity> einer persistenten Workflowinstanz abzurufen, wird die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet. Die <xref:System.Activities.WorkflowApplication.GetInstance%2A>-Methode verwendet die <xref:System.Activities.WorkflowApplication.Id%2A> der persistenten Workflowinstanz und den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, der die persistente Instanz enthält und <xref:System.Activities.WorkflowApplicationInstance> zurückgibt. <xref:System.Activities.WorkflowApplicationInstance> enthält Informationen über eine persistente Workflowinstanz, einschließlich der zugeordneten <xref:System.Activities.WorkflowIdentity>. Diese zugeordnete <xref:System.Activities.WorkflowIdentity> kann vom Host verwendet werden, um die richtige Workflowdefinition bereitzustellen, wenn die Workflowinstanz geladen und fortgesetzt wird.  
  
> [!NOTE]
>  Eine leere <xref:System.Activities.WorkflowIdentity> ist gültig und kann vom Host verwendet werden, um Instanzen, die ohne zugeordnete <xref:System.Activities.WorkflowIdentity> gespeichert wurden, der richtigen Workflowdefinition zuzuordnen. Dieses Szenario tritt auf, wenn eine Workflowanwendung zunächst ohne Workflowversionsverwaltung geschrieben wurde oder wenn eine Anwendung von [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] aktualisiert wird. Weitere Informationen finden Sie unter [Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung Workflowversionsverwaltung](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).  
  
 Im folgenden Beispiel eine `Dictionary<WorkflowIdentity, Activity>` wird zum Zuordnen <xref:System.Activities.WorkflowIdentity> -Instanzen mit die entsprechenden workflowdefinitionen und ein Workflow gestartet wird, mithilfe der `MortgageWorkflow` Workflowdefinition zugeordnet ist die `identityV1` <xref:System.Activities.WorkflowIdentity>.  
  
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
>  Wenn die <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft festgelegt wird, muss sie mit derselben <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Instanz festgelegt werden, die von <xref:System.Activities.WorkflowApplicationInstance> verwendet wird, da andernfalls <xref:System.ArgumentException> mit der folgenden Meldung ausgelöst wird: `The instance is configured with a different InstanceStore than this WorkflowApplication.`  
  
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
  
## <a name="UpdatingWF4PersistenceDatabases"></a> Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflowversionsverwaltung  
 Ein SqlWorkflowInstanceStoreSchemaUpgrade.sql-Datenbankskript wird bereitgestellt, um ein Upgrade für Persistenzdatenbanken auszuführen, die mit [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]-Datenbankskripts erstellt wurden. Durch dieses Skript werden die Datenbanken aktualisiert, um die neuen mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] eingeführten Versionsverwaltungsfunktionen zu unterstützen. Den persistenten Workflowinstanzen in den Datenbanken werden Standardversionswerte zugeordnet, und sie können an einer parallelen Ausführung und an dynamischen Updates beteiligt sein.  
  
 Wenn eine [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]-Workflowanwendung versucht, einen beliebigen Persistenzvorgang auszuführen, der die neuen Versionsverwaltungsfunktionen für eine Persistenzdatenbank verwendet, die nicht mithilfe des bereitgestellten Skripts aktualisiert wurde, wird eine <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> mit etwa folgender Meldung ausgelöst.  
  
 **Der SqlWorkflowInstanceStore weist die Datenbankversion "'4.0.0.0". InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' kann nicht für diese Datenbankversion ausgeführt werden.  Aktualisieren Sie die Datenbank auf "4.5.0.0".**  
### <a name="ToUpgrade"></a> Das Datenbankschema aktualisieren.  
  
1. Öffnen Sie SQL Server Management Studio und verbinden Sie mit dem Persistenzdatenbank-Server, z. B. **. \SQLEXPRESS**.  
  
2. Wählen Sie **öffnen**, **Datei** aus der **Datei** Menü. Wechseln Sie zum folgenden Ordner: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`  
  
3. Wählen Sie **SqlWorkflowInstanceStoreSchemaUpgrade.sql** , und klicken Sie auf **öffnen**.  
  
4. Wählen Sie den Namen der Persistenzdatenbank in der **verfügbaren Datenbanken** Dropdownliste aus.  
  
5. Wählen Sie **Execute** aus der **Abfrage** Menü.  
  
 Sobald die Abfrage abgeschlossen ist, wird das Datenbankschema aktualisiert. Sie können jetzt die standardmäßige Workflowidentität anzeigen, die den persistenten Workflowinstanzen zugewiesen wurde. Erweitern Sie die Persistenzdatenbank in der **Datenbanken** Knoten die **Objekt-Explorer**, und erweitern Sie dann die **Ansichten** Knoten. Mit der rechten Maustaste **System.Activities.DurableInstancing.Instances** , und wählen Sie **oberste 1000 Zeilen auswählen**. Einen Bildlauf zum Ende der Spalten aus, und beachten Sie, dass sechs zusätzliche Spalten der Sicht hinzugefügt: **IdentityName**, **IdentityPackage**, **erstellen**, **wichtigen**, **kleinere**, und **Revision**. Alle persistenten Workflows weisen den Wert **NULL** für diese Felder, die eine leere workflowidentität hinweist darstellt.
