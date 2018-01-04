---
title: Workflowpersistenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e65f07fc01d0d364d7271c4f1378b968b687881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-persistence"></a><span data-ttu-id="ec43f-102">Workflowpersistenz</span><span class="sxs-lookup"><span data-stu-id="ec43f-102">Workflow Persistence</span></span>
<span data-ttu-id="ec43f-103">Workflowpersistenz bezeichnet die dauerhafte Erfassung des Zustands einer Workflowinstanz unabhängig von Prozess- oder Computerinformationen.</span><span class="sxs-lookup"><span data-stu-id="ec43f-103">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="ec43f-104">Sie wird durchgeführt, um einen bekannten Wiederherstellungspunkt für die Workflowinstanz im Fall eines Systemfehlers bereitzustellen oder um Arbeitsspeicher beizubehalten, indem Workflowinstanzen entladen werden, die gerade nicht aktiv sind, bzw. um den Zustand der Workflowinstanz von einem Knoten zu einem anderen Knoten in einer Serverfarm zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="ec43f-104">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="ec43f-105">Die Persistenz aktiviert die Flexibilität, Skalierbarkeit und Wiederherstellung von Prozessen bei einem Fehler und bietet die Möglichkeit, den Arbeitsspeicher effizienter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ec43f-105">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="ec43f-106">Der Persistenzvorgang umfasst die Identifikation eines Persistenzpunkts, das Sammeln der zu speichernden Daten und schließlich die Delegierung des tatsächlichen Speichers der Daten an einen Persistenzanbieter.</span><span class="sxs-lookup"><span data-stu-id="ec43f-106">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="ec43f-107">Um die Persistenz für einen Workflow zu aktivieren, müssen Sie mit einen Instanzspeicher Zuordnen der **WorkflowApplication** oder **WorkflowServiceHost** Siehe [wie: Aktivieren der Persistenz für Workflows und Workflowdienste](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="ec43f-107">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="ec43f-108">Die **WorkflowApplication** und **WorkflowServiceHost** verwenden Sie den Instanzspeicher, die ihnen zugeordneten zum Beibehalten von Workflowinstanzen in einem persistenten Speicher und das Laden von Workflowinstanzen in aktivieren Arbeitsspeicher auf Grundlage der im persistenten Speicher gespeicherten workflowinstanzdaten.</span><span class="sxs-lookup"><span data-stu-id="ec43f-108">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="ec43f-109">Die [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] im Lieferumfang der **SqlWorkflowInstanceStore** -Klasse, die Persistenz von Daten und Metadaten zu Workflowinstanzen in einer SQL Server 2005 oder SQL Server 2008-Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ec43f-109">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="ec43f-110">Finden Sie unter [SQL-Workflowinstanzspeicher](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) Weitere Details.</span><span class="sxs-lookup"><span data-stu-id="ec43f-110">See [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="ec43f-111">Zum Speichern und Laden Ihrer anwendungsspezifischen Daten zusammen mit den Informationen zur Workflowinstanz können Sie Persistenzteilnehmer erstellen, die die <xref:System.Activities.Persistence.PersistenceParticipant>-Klasse erweitern.</span><span class="sxs-lookup"><span data-stu-id="ec43f-111">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="ec43f-112">Ein Persistenzteilnehmer nimmt am Persistenzvorgang teil, um benutzerdefinierte serialisierbare Daten in den persistenten Speicher zu speichern, die Daten aus dem Instanzspeicher in den Arbeitsspeicher zu laden und ggf. die zusätzliche Logik einer Persistenztransaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ec43f-112">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="ec43f-113">Weitere Informationen finden Sie unter [Persistenzteilnehmer](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span><span class="sxs-lookup"><span data-stu-id="ec43f-113">For more information, see [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span></span>  
  
 <span data-ttu-id="ec43f-114">Windows Server AppFabric vereinfacht die Konfiguration von Persistenz.</span><span class="sxs-lookup"><span data-stu-id="ec43f-114">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="ec43f-115">[Persistenz Konzepte mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span><span class="sxs-lookup"><span data-stu-id="ec43f-115"> [Persistence Concepts with Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="ec43f-116">Implizite Persistenzpunkte</span><span class="sxs-lookup"><span data-stu-id="ec43f-116">Implicit Persistence Points</span></span>  
 <span data-ttu-id="ec43f-117">Die folgende Liste enthält Beispiele der Bedingungen, zu denen ein Workflow beibehalten wird, wenn ein Instanzspeicher einem Workflow zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ec43f-117">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
-   <span data-ttu-id="ec43f-118">Wenn eine **TransactionScope** Aktivität abgeschlossen wird oder ein **TransactedReceiveScope** Aktivität abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ec43f-118">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
-   <span data-ttu-id="ec43f-119">Wenn eine Workflowinstanz im Leerlauf ist und die **WorkflowIdleBehavior** auf den Workflowhost festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ec43f-119">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="ec43f-120">In diesem Fall z. B. Wenn Sie messagingaktivitäten verwenden oder eine **Verzögerung** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ec43f-120">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
-   <span data-ttu-id="ec43f-121">Wenn eine Leerlauf und der **PersistableIdle** der Anwendung ist-Eigenschaftensatz auf **PersistableIdleAction.Persist**.</span><span class="sxs-lookup"><span data-stu-id="ec43f-121">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
-   <span data-ttu-id="ec43f-122">Wenn eine Hostanwendung angewiesen ist, eine Workflowinstanz beizubehalten oder zu entladen.</span><span class="sxs-lookup"><span data-stu-id="ec43f-122">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
-   <span data-ttu-id="ec43f-123">Wenn eine Workflowinstanz beendet oder fertig gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ec43f-123">When a workflow instance is terminated or finishes.</span></span>  
  
-   <span data-ttu-id="ec43f-124">Wenn eine **Persist** Aktivität ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ec43f-124">When a **Persist** activity executes.</span></span>  
  
-   <span data-ttu-id="ec43f-125">Wenn eine Instanz eines Workflows, die mit einer früheren Version von Windows Workflow Foundation entwickelt wurde, während einer interoperablen Ausführung auf einen Persistenzpunkt trifft.</span><span class="sxs-lookup"><span data-stu-id="ec43f-125">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec43f-126">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ec43f-126">In This Section</span></span>  
  
-   [<span data-ttu-id="ec43f-127">SQL-Workflowinstanzspeicher</span><span class="sxs-lookup"><span data-stu-id="ec43f-127">SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="ec43f-128">Instanzspeicher</span><span class="sxs-lookup"><span data-stu-id="ec43f-128">Instance Stores</span></span>](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [<span data-ttu-id="ec43f-129">Persistenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="ec43f-129">Persistence Participants</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [<span data-ttu-id="ec43f-130">Empfohlene Vorgehensweisen für die Persistenz</span><span class="sxs-lookup"><span data-stu-id="ec43f-130">Persistence Best Practices</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [<span data-ttu-id="ec43f-131">Nicht beibehaltene Workflowinstanzen</span><span class="sxs-lookup"><span data-stu-id="ec43f-131">Non-Persisted Workflow Instances</span></span>](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [<span data-ttu-id="ec43f-132">Anhalten und Fortsetzen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="ec43f-132">Pausing and Resuming a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
