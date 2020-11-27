---
title: Lesezeichenresolver für WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 6bcf1c1ac7c0ac9e385c4259ba085ab63afd7cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274607"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a><span data-ttu-id="ceff6-102">Lesezeichenresolver für WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="ceff6-102">Bookmark Resolver for WorkflowHostingEndpoint</span></span>

<span data-ttu-id="ceff6-103">In diesem Beispiel wird veranschaulicht, wie der <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> verwendet werden kann, um Workflowinstanzen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ceff6-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ceff6-104">Zeigt</span><span class="sxs-lookup"><span data-stu-id="ceff6-104">Demonstrates</span></span>  

 <span data-ttu-id="ceff6-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="ceff6-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ceff6-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="ceff6-106">Discussion</span></span>  

 <span data-ttu-id="ceff6-107">In diesem Beispiel wird <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet, um Workflowinstanzen zu erstellen, die mithilfe von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ceff6-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create workflow instances hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="ceff6-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ist ein Erweiterungspunkt für <xref:System.ServiceModel.Activities.WorkflowServiceHost>, der in den folgenden Szenarien verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="ceff6-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
- <span data-ttu-id="ceff6-109">Erstellen neuer Workflowinstanzen</span><span class="sxs-lookup"><span data-stu-id="ceff6-109">Creating new workflow instances.</span></span>  
  
- <span data-ttu-id="ceff6-110">Fortsetzen von Lesezeichen für eine auf <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="ceff6-110">Resuming bookmarks on workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="ceff6-111">Der enthaltene Beispielendpunkt macht einen Vertrag verfügbar, mit dem Vorgänge zum Erstellen eines Workflows bereitgestellt werden, und gibt die Instanz-ID zurück oder erstellt eine Instanz mit einer bestimmten ID.</span><span class="sxs-lookup"><span data-stu-id="ceff6-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and returns the instance ID or creates an instance with a specific ID.</span></span> <span data-ttu-id="ceff6-112">Die Beispielkonsolenanwendung erstellt eine <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz mit einer Workflowdefinition und fügt dem Host einen `CreationEndpoint` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ceff6-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a workflow definition and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="ceff6-113">Sie ruft dann den `Create`-Vorgang auf dem Endpunkt auf, um eine neue Workflowinstanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ceff6-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ceff6-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ceff6-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ceff6-115">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ceff6-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="ceff6-116">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="ceff6-116">Run the application.</span></span> <span data-ttu-id="ceff6-117">Die `CreationEndpoint`-Konsole zeigt eine Meldung an, die die Instanz-ID enthält, wenn die Workflowinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ceff6-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="ceff6-118">Die Meldung "Hallo Welt!"</span><span class="sxs-lookup"><span data-stu-id="ceff6-118">The message "Hello World!"</span></span> <span data-ttu-id="ceff6-119">wird von der Workflow Instanz ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ceff6-119">is printed by the workflow instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ceff6-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ceff6-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ceff6-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ceff6-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ceff6-122">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ceff6-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ceff6-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ceff6-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
