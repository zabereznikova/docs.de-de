---
title: Lesezeichenresolver für WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 48053ec7882b2e742b61fdc293b6bc5f8a129ca5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208568"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a><span data-ttu-id="da510-102">Lesezeichenresolver für WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="da510-102">Bookmark Resolver for WorkflowHostingEndpoint</span></span>
<span data-ttu-id="da510-103">In diesem Beispiel wird veranschaulicht, wie der <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> verwendet werden kann, um Workflowinstanzen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da510-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="da510-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="da510-104">Demonstrates</span></span>  
 <span data-ttu-id="da510-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="da510-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="da510-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="da510-106">Discussion</span></span>  
 <span data-ttu-id="da510-107">In diesem Beispiel wird <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet, um Workflowinstanzen zu erstellen, die mithilfe von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="da510-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create workflow instances hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="da510-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ist ein Erweiterungspunkt für <xref:System.ServiceModel.Activities.WorkflowServiceHost>, der in den folgenden Szenarien verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="da510-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="da510-109">Erstellen neuer Workflowinstanzen</span><span class="sxs-lookup"><span data-stu-id="da510-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="da510-110">Fortsetzen von Lesezeichen für eine auf <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="da510-110">Resuming bookmarks on workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="da510-111">Der enthaltene Beispielendpunkt macht einen Vertrag verfügbar, mit dem Vorgänge zum Erstellen eines Workflows bereitgestellt werden, und gibt die Instanz-ID zurück oder erstellt eine Instanz mit einer bestimmten ID.</span><span class="sxs-lookup"><span data-stu-id="da510-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and returns the instance ID or creates an instance with a specific ID.</span></span> <span data-ttu-id="da510-112">Die Beispielkonsolenanwendung erstellt eine <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz mit einer Workflowdefinition und fügt dem Host einen `CreationEndpoint` hinzu.</span><span class="sxs-lookup"><span data-stu-id="da510-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a workflow definition and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="da510-113">Sie ruft dann den `Create`-Vorgang auf dem Endpunkt auf, um eine neue Workflowinstanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da510-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="da510-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="da510-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="da510-115">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="da510-115">Build the solution.</span></span>  
  
2.  <span data-ttu-id="da510-116">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="da510-116">Run the application.</span></span> <span data-ttu-id="da510-117">Die `CreationEndpoint`-Konsole zeigt eine Meldung an, die die Instanz-ID enthält, wenn die Workflowinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="da510-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="da510-118">Die Meldung "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="da510-118">The message "Hello World!"</span></span> <span data-ttu-id="da510-119">wird von der Workflowinstanz ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="da510-119">is printed by the workflow instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="da510-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="da510-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="da510-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="da510-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="da510-122">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="da510-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="da510-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="da510-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
