---
title: "Permanente Verzögerung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0e679b91bd342ed5105fba7b916a8ed0070d0da
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="durable-delay"></a><span data-ttu-id="13862-102">Permanente Verzögerung</span><span class="sxs-lookup"><span data-stu-id="13862-102">Durable Delay</span></span>
<span data-ttu-id="13862-103">In diesem Beispiel wird veranschaulicht, wie eine permanente Verzögerung verwendet wird, eine Verzögerung, die den Workflow während der Verzögerung auf einem permanenten Gerät beibehält.</span><span class="sxs-lookup"><span data-stu-id="13862-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="13862-104">Der Beispielworkflow enthält zwei Meldungen an die Konsole, die durch eine Verzögerung getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="13862-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="13862-105">Wenn die Verzögerung ausgelöst wird, wird der Workflow entladen und verbleibt 5 Sekunden im Workflowinstanzspeicher, bevor er erneut in den Speicher geladen wird.</span><span class="sxs-lookup"><span data-stu-id="13862-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="13862-106">Workflowdetails</span><span class="sxs-lookup"><span data-stu-id="13862-106">Workflow Details</span></span>  
 <span data-ttu-id="13862-107">Der Workflowdiensthost hostet den Workflow und verwaltet die Workflowinstanzen durch Laden und Entladen.</span><span class="sxs-lookup"><span data-stu-id="13862-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="13862-108">Zum Starten einer Instanz der Workflowdefinition wird im Beispiel ein Proxy festgelegt, der eine Meldung an die <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow sendet.</span><span class="sxs-lookup"><span data-stu-id="13862-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="13862-109">Die <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>-Eigenschaft wird auf `true` festgelegt, sodass eine neue Instanz des Workflows erstellt werden kann, sobald eine Meldung empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="13862-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="13862-110">Die folgende Liste enthält das Setup des Workflowdiensthosts während der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="13862-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="13862-111">Erstellt einen Diensthost mit einer Adresse (http://localhost:8080/Client).</span><span class="sxs-lookup"><span data-stu-id="13862-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="13862-112">Erstellt einen Endpunkt im Diensthost, um Kommunikation mit der <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="13862-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="13862-113">Richtet einen SQL-Instanzspeicher ein.</span><span class="sxs-lookup"><span data-stu-id="13862-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="13862-114">Fügt ein Verhalten zum Entladen von Instanzen hinzu, das die Bedingungen angibt, unter denen der Workflowdiensthost eine Workflowinstanz in den SQL-Persistenzspeicher entladen soll.</span><span class="sxs-lookup"><span data-stu-id="13862-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="13862-115">Für dieses Beispiel wird die Instanz entladen, unmittelbar nachdem der Workflow in den Leerlauf eintritt (wenn die Verzögerung ausgelöst wird).</span><span class="sxs-lookup"><span data-stu-id="13862-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="13862-116">Erstellt den Proxy, der eine Meldung an die <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow sendet.</span><span class="sxs-lookup"><span data-stu-id="13862-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="13862-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="13862-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="13862-118">Richten Sie die Persistenzdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="13862-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="13862-119">Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="13862-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="13862-120">Navigieren Sie zu der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Verzeichnis (C:\Windows\Microsoft.NET\Framework\v4. X\\).</span><span class="sxs-lookup"><span data-stu-id="13862-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="13862-121">Bearbeiten Sie die Datei "WorkflowManagementService.exe.config", und fügen Sie die folgende Verbindungszeichenfolge im <`database`>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="13862-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="13862-122">Navigieren Sie zum Verzeichnis DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="13862-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="13862-123">Führen Sie Setup.cmd aus.</span><span class="sxs-lookup"><span data-stu-id="13862-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="13862-124">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erhöhten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="13862-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="13862-125">Öffnen Sie die Projektmappendatei "Delay.sln".</span><span class="sxs-lookup"><span data-stu-id="13862-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="13862-126">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="13862-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="13862-127">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="13862-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="13862-128">So deinstallieren Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="13862-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="13862-129">Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="13862-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="13862-130">Navigieren Sie zum Verzeichnis DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="13862-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="13862-131">Führen Sie die Datei "Cleanup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="13862-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13862-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="13862-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="13862-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="13862-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="13862-134">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="13862-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13862-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="13862-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`