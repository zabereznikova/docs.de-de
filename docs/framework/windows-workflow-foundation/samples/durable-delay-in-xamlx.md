---
title: "Permanente Verzögerung in XAMLX"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff5eb09acea16ac125fac5d9e3ed875c9095e1c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="873b8-102">Permanente Verzögerung in XAMLX</span><span class="sxs-lookup"><span data-stu-id="873b8-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="873b8-103">In diesem Beispiel wird veranschaulicht, wie eine permanente Verzögerung verwendet wird, eine Verzögerung, die den Workflow während der Verzögerung auf einem permanenten Gerät beibehält.</span><span class="sxs-lookup"><span data-stu-id="873b8-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="873b8-104">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="873b8-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="873b8-105">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="873b8-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="873b8-106">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="873b8-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="873b8-107">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="873b8-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="873b8-108">Diskussion</span><span class="sxs-lookup"><span data-stu-id="873b8-108">Discussion</span></span>  
 <span data-ttu-id="873b8-109">Der Beispielworkflow enthält zwei Meldungen zu einer lokalen Datei, die durch eine Verzögerung getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="873b8-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="873b8-110">Wenn die Verzögerung ausgelöst wird, wird der Workflow entladen und verbleibt 5 Sekunden im Workflowinstanzspeicher, bevor er erneut in den Speicher geladen wird.</span><span class="sxs-lookup"><span data-stu-id="873b8-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="873b8-111">Die XAMLX-Datei ist ein Workflowdienst, der in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="873b8-111">The .xamlx file is a workflow service that is hosted in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="873b8-112"> verwendet Cassini, das einen Workflowdiensthost zum Hosten des Workflows nutzt.</span><span class="sxs-lookup"><span data-stu-id="873b8-112"> uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="873b8-113">Neben dem Hosten des Workflows verwaltet der Workflowdiensthost die Workflowinstanzen durch Laden und Entladen.</span><span class="sxs-lookup"><span data-stu-id="873b8-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="873b8-114">Um eine Instanz der [!INCLUDE[wf](../../../../includes/wf-md.md)]-Definition (auf dem Workflowdiensthost) zu starten, legen Sie einen Client fest, der eine Nachricht an die <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow sendet.</span><span class="sxs-lookup"><span data-stu-id="873b8-114">To start an instance of the [!INCLUDE[wf](../../../../includes/wf-md.md)] definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="873b8-115">Die <xref:System.ServiceModel.Activities.Receive>-Eigenschaft von <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> ist auf `true` festgelegt, sodass eine neue Instanz des Workflows erstellt werden kann, sobald eine Nachricht empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="873b8-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="873b8-116">Während der Initialisierung wird der Konfigurationsdatei, die den Workflowdiensthost angibt, unter dem eine Instanz in den Persistenzspeicher (Datenbank) entladen werden soll, ein Verhalten zum Entladen von Instanzen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="873b8-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="873b8-117">Für dieses Beispiel wird die Instanz entladen, unmittelbar nachdem der Workflow in den Leerlauf eintritt (wenn die Verzögerung ausgelöst wird).</span><span class="sxs-lookup"><span data-stu-id="873b8-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="873b8-118">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="873b8-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="873b8-119">Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="873b8-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="873b8-120">Navigieren Sie zum Ordner "DurableDelayXamlx\CS".</span><span class="sxs-lookup"><span data-stu-id="873b8-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="873b8-121">Führen Sie Setup.cmd aus.</span><span class="sxs-lookup"><span data-stu-id="873b8-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="873b8-122">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="873b8-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="873b8-123">Öffnen Sie die Projektmappendatei "DurableDelayXamlx.sln".</span><span class="sxs-lookup"><span data-stu-id="873b8-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="873b8-124">In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="873b8-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="873b8-125">Wählen Sie **mehrere Startprojekte** , und legen Sie beide Projekte auf **starten**.</span><span class="sxs-lookup"><span data-stu-id="873b8-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="873b8-126">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="873b8-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="873b8-127">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="873b8-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="873b8-128">So deinstallieren Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="873b8-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="873b8-129">Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="873b8-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="873b8-130">Navigieren Sie zum Ordner "DurableDelayXamlx\CS".</span><span class="sxs-lookup"><span data-stu-id="873b8-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="873b8-131">Führen Sie die Datei "Cleanup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="873b8-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="873b8-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="873b8-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="873b8-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="873b8-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="873b8-134">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="873b8-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="873b8-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="873b8-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
