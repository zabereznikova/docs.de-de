---
title: Zwischenspeichern von Channels mit Send
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f8a11397fe161edad6f726c1d6df9ed09dad54a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="channel-caching-with-send"></a><span data-ttu-id="2648d-102">Zwischenspeichern von Channels mit Send</span><span class="sxs-lookup"><span data-stu-id="2648d-102">Channel Caching with Send</span></span>
<span data-ttu-id="2648d-103">Der <xref:System.ServiceModel.Activities.SendMessageChannelCache> ermöglicht unterschiedliche Ebenen des Zwischenspeicherns von Channels mit der <xref:System.ServiceModel.Activities.Send>-Aktivität und der <xref:System.ServiceModel.Activities.SendParametersContent>-Aktivität für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2648d-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> enables users to have different levels of channel caching with <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendParametersContent> activities.</span></span> <span data-ttu-id="2648d-104">Das Zwischenspeichern auf Instanzebene ist standardmäßig aktiviert, und in diesem Beispiel werden die folgenden Funktionen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2648d-104">Instance-level caching is enabled by default and this sample demonstrates the following features:</span></span>  
  
1.  <span data-ttu-id="2648d-105">Freigeben eines <xref:System.ServiceModel.Activities.SendMessageChannelCache> über eine Anwendungsdomäne hinweg.</span><span class="sxs-lookup"><span data-stu-id="2648d-105">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> across an application domain.</span></span>  
  
2.  <span data-ttu-id="2648d-106">Deaktivieren Sie des Zwischenspeicherns von Channels.</span><span class="sxs-lookup"><span data-stu-id="2648d-106">Disable channel caching.</span></span>  
  
3.  <span data-ttu-id="2648d-107">Freigeben eines <xref:System.ServiceModel.Activities.SendMessageChannelCache> in Workflowinstanzen in einem <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="2648d-107">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> among workflow instances in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2648d-108">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="2648d-108">Demonstrates</span></span>  
 <span data-ttu-id="2648d-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache>-Erweiterung, <xref:System.ServiceModel.Activities.Send>-Aktivität, <xref:System.ServiceModel.Activities.Receive>-Aktivität, <xref:System.ServiceModel.Activities.ReceiveContent>-Aktivität und <xref:System.ServiceModel.Activities.SendReply>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2648d-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> extension, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2648d-110">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="2648d-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2648d-111">Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2648d-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="2648d-112">Führen Sie die unter "\EchoWorkflowService\bin\debug generierte Anwendung "EchoWorkflowService" aus.</span><span class="sxs-lookup"><span data-stu-id="2648d-112">Run the EchoWorkflowService application generated in \EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="2648d-113">Führen Sie die unter "\EchoWorkflowClient\bin\debug" generierte Anwendung "EchoWorkflowClient" aus.</span><span class="sxs-lookup"><span data-stu-id="2648d-113">Run the EchoWorkflowClient application generated in .\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="2648d-114">Der Client ruft den Echo-Vorgang für den Dienst auf, und gibt die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="2648d-114">The client calls the Echo operation on the service and prints the results.</span></span> <span data-ttu-id="2648d-115">Wenn die Ergebnisse ausgegeben wurden, drücken Sie die EINGABETASTE, um den Client und den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2648d-115">When the results have been printed, press ENTER to exit the client and the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2648d-116">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2648d-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2648d-117">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2648d-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2648d-118">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2648d-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2648d-119">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2648d-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
