---
title: Erweiterbarkeit des Speichers
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 46c1ea40925a5c79180171da9a705d7e6b7c8b89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641605"
---
# <a name="store-extensibility"></a><span data-ttu-id="24ead-102">Erweiterbarkeit des Speichers</span><span class="sxs-lookup"><span data-stu-id="24ead-102">Store Extensibility</span></span>

<span data-ttu-id="24ead-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> ermöglicht es Benutzern, benutzerdefinierte, anwendungsspezifische Eigenschaften höher zu stufen, die verwendet werden können, um Instanzen in der Persistenzdatenbank abzufragen.</span><span class="sxs-lookup"><span data-stu-id="24ead-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> allows users to promote custom, application-specific properties that can be used to query for instances in the persistence database.</span></span> <span data-ttu-id="24ead-104">Durch das Höherstufen einer Eigenschaft ist der Wert in einer besonderen Ansicht in der Datenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24ead-104">The act of promoting a property causes the value to be available within a special view in the database.</span></span> <span data-ttu-id="24ead-105">Diese höhergestuften Eigenschaften sind Eigenschaften, die in Benutzerabfragen verwendet werden können. Dabei kann es sich um einfache Typen wie Int64, Guid, String und DateTime oder um einen serialisierten Binärtyp (byte[]) handeln.</span><span class="sxs-lookup"><span data-stu-id="24ead-105">These promoted properties (properties that can be used in user queries) can be of simple types such as Int64, Guid, String, and DateTime or of a serialized binary type (byte[]).</span></span>

<span data-ttu-id="24ead-106">Die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Klasse verfügt über die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A>-Methode, mit der Sie eine Eigenschaft zu einer Eigenschaft hochstufen können, die in Abfragen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="24ead-106">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class has the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> method that you can use to promote a property as a property that can be used in queries.</span></span> <span data-ttu-id="24ead-107">Das folgende Beispiel ist ein End-to-End-Beispiel für die Erweiterbarkeit des Speichers.</span><span class="sxs-lookup"><span data-stu-id="24ead-107">The following example is an end-to-end example of store extensibility.</span></span>

1. <span data-ttu-id="24ead-108">In diesem Beispielszenario verfügt eine Anwendung zur Dokumentverarbeitung (DP) über Workflows, die benutzerdefinierte Aktivitäten zur Verarbeitung von Dokumenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="24ead-108">In this example scenario, a document processing (DP) application has workflows, each of which uses custom activities for document processing.</span></span> <span data-ttu-id="24ead-109">Diese Workflows enthalten einen Satz von Zustandsvariablen, die für den Endbenutzer sichtbar sein müssen.</span><span class="sxs-lookup"><span data-stu-id="24ead-109">These workflows have a set of state variables that need to be made visible to the end user.</span></span> <span data-ttu-id="24ead-110">Um dies zu erreichen, stellt die DP-Anwendung eine Instanzerweiterung des Typs <xref:System.Activities.Persistence.PersistenceParticipant> bereit, die von Aktivitäten dazu verwendet wird, Zustandsvariablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="24ead-110">To achieve this, the DP application provides an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span>

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        public string DocumentId;
        public string ApprovalStatus;
        public string UserName;
        public DateTime LastUpdateTime;
    }
    ```

2. <span data-ttu-id="24ead-111">Die neue Erweiterung wird dann dem Host hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="24ead-111">The new extension is then added to the host.</span></span>

    ```csharp
    static Activity workflow = CreateWorkflow();
    WorkflowApplication application = new WorkflowApplication(workflow);
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();
    application.Extensions.Add(documentStatusExtension);
    ```

     <span data-ttu-id="24ead-112">Weitere Informationen zum Hinzufügen eines benutzerdefinierten persistenzteilnehmers finden Sie unter den [Persistenzteilnehmer](persistence-participants.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="24ead-112">For more details about adding a custom persistence participant, see the [Persistence Participants](persistence-participants.md) sample.</span></span>

3. <span data-ttu-id="24ead-113">Die benutzerdefinierten Aktivitäten in der DP-Anwendung füllen verschiedene Statusfelder in der **Execute** Methode.</span><span class="sxs-lookup"><span data-stu-id="24ead-113">The custom activities in the DP application populate various status fields in the **Execute** method.</span></span>

    ```csharp
    public override void Execute(CodeActivityContext context)
    {
        // ...
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();
        // ...
    }
    ```

4. <span data-ttu-id="24ead-114">Wenn eine Workflowinstanz einen Persistenzpunkt erreicht die **CollectValues** Methode der **DocumentStatusExtension** persistenzteilnehmer speichert diese Eigenschaften in den persistenzdaten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="24ead-114">When a workflow instance reaches a persistence point, the **CollectValues** method of the **DocumentStatusExtension** persistence participant saves these properties into the persistence data collection.</span></span>

    ```csharp
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
    > <span data-ttu-id="24ead-115">Alle diese Eigenschaften werden an übergeben **SqlWorkflowInstanceStore** vom persistenzframework über die **SqlWorkflowInstanceStore** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="24ead-115">All these properties are passed to **SqlWorkflowInstanceStore** by the persistence framework through the **SaveWorkflowCommand.InstanceData** collection.</span></span>

5. <span data-ttu-id="24ead-116">Die DP-Anwendung initialisiert den SQL-Workflow-Instanz-Store, und ruft die **höher stufen** Methode, um diese Daten höher zu stufen.</span><span class="sxs-lookup"><span data-stu-id="24ead-116">The DP application initializes the SQL Workflow Instance Store and invokes the **Promote** method to promote this data.</span></span>

    ```csharp
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

    <span data-ttu-id="24ead-117">Anhand dieser Informationen für die Höherstufung **SqlWorkflowInstanceStore** platziert die Dateneigenschaften in den Spalten von der ["instancepromotedproperties"](#InstancePromotedProperties) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="24ead-117">Based on this promotion information, **SqlWorkflowInstanceStore** places the data properties in the columns of the [InstancePromotedProperties](#InstancePromotedProperties) view.</span></span>

6. <span data-ttu-id="24ead-118">Um eine Teilmenge der Daten aus der Höherstufungstabelle abzufragen, fügt die DP-Anwendung oben in der Höherstufungsansicht eine benutzerdefinierte Ansicht hinzu.</span><span class="sxs-lookup"><span data-stu-id="24ead-118">To query a subset of the data from the promotion table, the DP application adds a customized view on top of the promotion view.</span></span>

    ```sql
    create view [dbo].[DocumentStatus] with schemabinding
    as
        select  P.[InstanceId] as [InstanceId],
            P.Value1 as [UserName],
            P.Value2 as [ApprovalStatus],
            P.Value3 as [DocumentId],
            P.Value4 as [LastUpdatedTime]
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P
    where P.PromotionName = N'DocumentStatus'
    go
    ```

## <a name="InstancePromotedProperties"></a> <span data-ttu-id="24ead-119">[System.Activities.DurableInstancing.InstancePromotedProperties]-Sicht</span><span class="sxs-lookup"><span data-stu-id="24ead-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span></span>

|<span data-ttu-id="24ead-120">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="24ead-120">Column Name</span></span>|<span data-ttu-id="24ead-121">Spaltentyp</span><span class="sxs-lookup"><span data-stu-id="24ead-121">Column Type</span></span>|<span data-ttu-id="24ead-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24ead-122">Description</span></span>|
|-----------------|-----------------|-----------------|
|<span data-ttu-id="24ead-123">InstanceId</span><span class="sxs-lookup"><span data-stu-id="24ead-123">InstanceId</span></span>|<span data-ttu-id="24ead-124">GUID</span><span class="sxs-lookup"><span data-stu-id="24ead-124">GUID</span></span>|<span data-ttu-id="24ead-125">Die Workflowinstanz, der diese Höherstufung angehört.</span><span class="sxs-lookup"><span data-stu-id="24ead-125">The workflow instance that this promotion belongs to.</span></span>|
|<span data-ttu-id="24ead-126">PromotionName</span><span class="sxs-lookup"><span data-stu-id="24ead-126">PromotionName</span></span>|<span data-ttu-id="24ead-127">nvarchar(400)</span><span class="sxs-lookup"><span data-stu-id="24ead-127">nvarchar(400)</span></span>|<span data-ttu-id="24ead-128">Der Name der Höherstufung.</span><span class="sxs-lookup"><span data-stu-id="24ead-128">The name of the promotion itself.</span></span>|
|<span data-ttu-id="24ead-129">Value1, Value2, Value3, ..., Value32</span><span class="sxs-lookup"><span data-stu-id="24ead-129">Value1, Value2, Value3,..,Value32</span></span>|<span data-ttu-id="24ead-130">sql_variant</span><span class="sxs-lookup"><span data-stu-id="24ead-130">sql_variant</span></span>|<span data-ttu-id="24ead-131">Der Wert der höhergestuften Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24ead-131">The value of the promoted property itself.</span></span> <span data-ttu-id="24ead-132">Die meisten primitiven Datentypen in SQL mit Ausnahme der binären Blobs und Zeichenfolgen über 8000 Byte Länge sind für sql_variant geeignet.</span><span class="sxs-lookup"><span data-stu-id="24ead-132">Most SQL primitive data types except binary blobs and strings over 8000 bytes in length can fit in sql_variant.</span></span>|
|<span data-ttu-id="24ead-133">Value33, Value34, Value35, …, Value64</span><span class="sxs-lookup"><span data-stu-id="24ead-133">Value33, Value34, Value35, …, Value64</span></span>|<span data-ttu-id="24ead-134">varbinary(max)</span><span class="sxs-lookup"><span data-stu-id="24ead-134">varbinary(max)</span></span>|<span data-ttu-id="24ead-135">Der Wert von höher gestuften Eigenschaften, die explizit als varbinary(max) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="24ead-135">The value of promoted properties that are explicitly declared as varbinary(max).</span></span>|
