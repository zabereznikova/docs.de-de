---
title: "Erweiterbarkeit des Speichers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Erweiterbarkeit des Speichers
<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> ermöglicht es Benutzern, benutzerdefinierte, anwendungsspezifische Eigenschaften höher zu stufen, die verwendet werden können, um Instanzen in der Persistenzdatenbank abzufragen.Durch das Höherstufen einer Eigenschaft ist der Wert in einer besonderen Ansicht in der Datenbank verfügbar.Diese höhergestuften Eigenschaften sind Eigenschaften, die in Benutzerabfragen verwendet werden können. Dabei kann es sich um einfache Typen wie Int64, Guid, String und DateTime oder um einen serialisierten Binärtyp \(byte\[\]\) handeln.  
  
 Die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>\-Klasse verfügt über die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A>\-Methode, mit der Sie eine Eigenschaft zu einer Eigenschaft hochstufen können, die in Abfragen verwendet werden kann.Das folgende Beispiel ist ein End\-to\-End\-Beispiel für die Erweiterbarkeit des Speichers.  
  
1.  In diesem Beispielszenario verfügt eine Anwendung zur Dokumentverarbeitung \(DP\) über Workflows, die benutzerdefinierte Aktivitäten zur Verarbeitung von Dokumenten verwenden.Diese Workflows enthalten einen Satz von Zustandsvariablen, die für den Endbenutzer sichtbar sein müssen.Um dies zu erreichen, stellt die DP\-Anwendung eine Instanzerweiterung des Typs <xref:System.Activities.Persistence.PersistenceParticipant> bereit, die von Aktivitäten dazu verwendet wird, Zustandsvariablen anzugeben.  
  
    ```  
  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        public string DocumentId;  
        public string ApprovalStatus;  
        public string UserName;  
        public DateTime LastUpdateTime;  
    }  
  
    ```  
  
2.  Die neue Erweiterung wird dann dem Host hinzugefügt.  
  
    ```  
    static Activity workflow = CreateWorkflow();  
    WorkflowApplication application = new WorkflowApplication(workflow);  
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();  
    application.Extensions.Add(documentStatusExtension);  
  
    ```  
  
     Weitere Details zum Hinzufügen eines benutzerdefinierten Persistenzteilnehmers finden Sie im [Persistenzteilnehmer](../../../docs/framework/windows-workflow-foundation//persistence-participants.md)\-Beispiel.  
  
3.  Die benutzerdefinierten Aktivitäten in der DP\-Anwendung füllen verschiedene Statusfelder in der **Execute**\-Methode auf.  
  
    ```  
  
    public override void Execute(CodeActivityContext context)  
    {  
        // ...  
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();  
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";  
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = “Approved”;  
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();  
        // ...  
    }  
  
    ```  
  
4.  Wenn eine Workflowinstanz einen Persistenzpunkt erreicht, speichert die **CollectValues**\-Methode des **DocumentStatusExtension** Persistenzteilnehmers diese Eigenschaften in die Persistenzdatensammlung.  
  
    ```  
  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");  
  
        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)  
        {  
            readWriteValues = new Dictionary<XName, object>();  
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);  
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);  
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);  
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);  
  
            writeOnlyValues = null;  
        }  
        // ...  
    }  
  
    ```  
  
    > [!NOTE]
    >  All diese Eigenschaften werden vom Persistenzframework über die **SaveWorkflowCommand.InstanceData**\-Auflistung an den **SqlWorkflowInstanceStore** übergeben.  
  
5.  Die DP\-Anwendung initialisiert den SQL\-Workflowinstanzspeicher und ruft die **Promote**\-Methode auf, um diese Daten höher zu stufen.  
  
    ```  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
  
    List<XName> variantProperties = new List<XName>()   
    {   
        xNS.GetName("UserName"),   
        xNS.GetName("ApprovalStatus"),   
        xNS.GetName("DocumentId"),   
        xNS.GetName("LastModifiedTime")   
    };  
  
    store.Promote("DocumentStatus", variantProperties, null);  
    ```  
  
     Auf Grundlage dieser Informationen für die Höherstufung fügt **SqlWorkflowInstanceStore** die Dateneigenschaften in die Spalten der [[System.Activities.DurableInstancing.InstancePromotedProperties]-Ansicht](../Topic/Store%20Extensibility.md#InstancePromotedProperties) ein.  
  
6.  Um eine Teilmenge der Daten aus der Höherstufungstabelle abzufragen, fügt die DP\-Anwendung oben in der Höherstufungsansicht eine benutzerdefinierte Ansicht hinzu.  
  
    ```  
  
    create view [dbo].[DocumentStatus] with schemabinding  
    as  
        select  P.[InstanceId] as [InstanceId],  
            P.Value1 as [UserName],  
            P.Value2 as [ApprovalStatus],  
            P.Value3 as [DocumentId],  
            P.Value4 as [LastUpdatedTime]  
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P  
    where P.PromotionName = N'DocumentStatus'  
    go  
  
    ```  
  
##  <a name="InstancePromotedProperties"></a> \[System.Activities.DurableInstancing.InstancePromotedProperties\]\-Ansicht  
  
|Spaltenname|Spaltentyp|Beschreibung|  
|-----------------|----------------|------------------|  
|InstanceId|GUID|Die Workflowinstanz, der diese Höherstufung angehört.|  
|PromotionName|nvarchar\(400\)|Der Name der Höherstufung.|  
|Value1, Value2, Value3, ..., Value32|sql\_variant|Der Wert der höhergestuften Eigenschaft.Die meisten primitiven Datentypen in SQL mit Ausnahme der binären Blobs und Zeichenfolgen über 8000 Byte Länge sind für sql\_variant geeignet.|  
|Value33, Value34, Value35, …, Value64|varbinary\(max\)|Der Wert von höher gestuften Eigenschaften, die explizit als varbinary\(max\) deklariert werden.|