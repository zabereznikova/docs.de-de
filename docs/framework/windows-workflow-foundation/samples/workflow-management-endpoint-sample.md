---
title: Workflowverwaltungsendpunkt (Beispiel)
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 3d99cbef20895381f5e40ee939e1d94a409f1391
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46485258"
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="b3e0f-102">Workflowverwaltungsendpunkt (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="b3e0f-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="b3e0f-103">In diesem Beispiel wird gezeigt, wie ein Workflowsteuerungsendpunkt verwendet werden kann, um Workflows sowohl lokal als auch remote zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="b3e0f-104">Das Beispiel veranschaulicht, wie ein Steuerungsendpunkt gehostet wird und Clients geschrieben werden, die den Steuerungsendpunkt aufrufen, um die Instanz eines Workflows zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="b3e0f-105">Der Workflow ist kein Dienst.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="b3e0f-106">Auf der Dienstseite des Beispiels wird ein Workflow mit WorkflowServiceHost gehostet und WorkflowControlEndpoint hinzugefügt, damit Clients Steuerungsvorgänge (Anhalten, Starten usw.) ausführen können.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="b3e0f-107">Ein benutzerdefinierter CreationEndpoint wird ebenfalls hinzugefügt, damit der Workflow erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="b3e0f-108">Der Dienst verwendet dann diese Endpunkte, um den Workflow in einem angehaltenen Zustand zu starten und anschließend fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="b3e0f-109">Der Client führt die gleichen Vorgänge aus, jedoch vom Clientcode aus.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-109">The client performs the same operations but from the client code.</span></span> <span data-ttu-id="b3e0f-110">Für Weitere Informationen zu diesen finden Sie unter Schnittstellen [Workflowsteuerungsendpunkt](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) und [Vorgehensweise: Hosten ein nicht-dienstworkflows in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="b3e0f-110">For more information about these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="b3e0f-111">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="b3e0f-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="b3e0f-112">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="b3e0f-113">Öffnen Sie die Projektmappe "ManagementEndpoint.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3e0f-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="b3e0f-114">Um die Projektmappe zu erstellen, drücken Sie STRG + UMSCHALT + B, oder wählen Sie **Projektmappe** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="b3e0f-115">Starten Sie die Anwendung "ManagementEndpoint.exe".</span><span class="sxs-lookup"><span data-stu-id="b3e0f-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="b3e0f-116">Starten Sie die Anwendung "Client.exe".</span><span class="sxs-lookup"><span data-stu-id="b3e0f-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b3e0f-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b3e0f-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b3e0f-119">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b3e0f-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b3e0f-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`