---
title: Toolboxdienst
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b3ea56d28d202bd8356fea1783b6675a708631d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516190"
---
# <a name="toolbox-service"></a><span data-ttu-id="ec2f3-102">Toolboxdienst</span><span class="sxs-lookup"><span data-stu-id="ec2f3-102">Toolbox Service</span></span>
<span data-ttu-id="ec2f3-103">Dieses Beispiel veranschaulicht, wie die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Toolboxaktivitäten auf Grundlage des Kontexts des Workflows aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-103">This sample demonstrates how to update the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] Toolbox activities based on the context of the workflow.</span></span> <span data-ttu-id="ec2f3-104">Das Beispiel enthält einen Workflow, der den Toolboxinhalt danach ändert, ob eine benutzerdefinierte Aktivität ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-104">The sample contains a workflow that changes the toolbox contents based on whether a custom activity is selected.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ec2f3-105">Diskussion</span><span class="sxs-lookup"><span data-stu-id="ec2f3-105">Discussion</span></span>  
 <span data-ttu-id="ec2f3-106">Während der Workflowerstellung soll die Toolbox im Allgemeinen kontextbezogen sein.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-106">During workflow authoring, customers generally want their Toolbox to be context sensitive.</span></span> <span data-ttu-id="ec2f3-107">Der Benutzer möchte z. B. sicherstellen, dass die Toolbox einige zusätzliche Aktivitäten anzeigt, wenn dem Workflow eine bestimmte Aktivität hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-107">For example, the user may want to ensure that the Toolbox shows a few additional activities when a specific activity is added to the workflow.</span></span> <span data-ttu-id="ec2f3-108">Wenn die Aktivitäten aus dem Workflow entfernt werden, sollte die Toolbox angemessen auf Grundlage der Domänenanforderungen reagieren.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-108">If the activities are removed from the workflow, the toolbox should react appropriately based on the domain requirements.</span></span>  
  
 <span data-ttu-id="ec2f3-109">In einem neu gehosteten Workflow-Designer steuern Sie das Toolbox-Steuerelement und können sicherstellen, dass der Host entsprechende Änderungen im Toolbox-Steuerelement auf Grundlage der Modelländerungen im Workflow auslöst.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-109">In a re-hosted workflow designer, you control the Toolbox control and can ensure that based on the Model changes in the workflow, the host triggers appropriate changes in the Toolbox control.</span></span> <span data-ttu-id="ec2f3-110">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] wird die Toolbox jedoch nicht vom Benutzer gesteuert, und deshalb ist eine Schnittstelle erforderlich, um den Inhalt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-110">However, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], the toolbox is not controlled by the user and thus an interface is required to modify its contents.</span></span> <span data-ttu-id="ec2f3-111">`IActivityToolboxService` ist diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-111">`IActivityToolboxService` is that interface.</span></span>  
  
 <span data-ttu-id="ec2f3-112">Die API stellt die folgenden vier Methoden bereit.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-112">The API provides the following four methods.</span></span>  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ec2f3-113">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ec2f3-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ec2f3-114">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "WorkflowSimulator.sln".</span><span class="sxs-lookup"><span data-stu-id="ec2f3-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WorkflowSimulator.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ec2f3-115">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-115">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ec2f3-116">Öffnen Sie die Datei "Workflow.xaml".</span><span class="sxs-lookup"><span data-stu-id="ec2f3-116">Open the Workflow.xaml file.</span></span>  
  
4.  <span data-ttu-id="ec2f3-117">Hinzufügen einer **CustomActivity** per Drag & Drop aus der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-117">Add a **CustomActivity** by dragging and dropping it from the toolbox.</span></span> <span data-ttu-id="ec2f3-118">Beachten Sie, die eine zusätzliche Toolboxkategorie: **neue WF-Kategorie** mit einer zusätzlichen Aktivität **zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-118">Notice that an additional Toolbox category called: **New WF Category** with an additional activity **Assign**.</span></span>  
  
5.  <span data-ttu-id="ec2f3-119">Deaktivieren Sie nun die **CustomActivity** durch eine andere Aktivität hinein ziehen.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-119">Now unselect the **CustomActivity** by dragging another activity into it.</span></span>  
  
6.  <span data-ttu-id="ec2f3-120">Das Element **zuweisen** in der Kategorie **neue WF-Kategorie** in der Toolbox wird jetzt entfernt.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-120">The item **Assign** in the category **New WF Category** under Toolbox is now removed.</span></span> <span data-ttu-id="ec2f3-121">Da es in der Kategorie keine Elemente mehr gibt, wird auch die Kategorie entfernt.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-121">Also, because there are no more items left in the category, the category is removed as well.</span></span>  
  
7.  <span data-ttu-id="ec2f3-122">Wählen Sie die **CustomActivity** erneut und die Kategorie und **zuweisen** Aktivität wieder hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-122">Select the **CustomActivity** again and the category and **Assign** activity is added back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec2f3-123">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ec2f3-124">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ec2f3-125">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec2f3-126">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ec2f3-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
