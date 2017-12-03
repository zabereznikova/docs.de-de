---
title: Verwenden von Interop mit dem External Data Exchange-Dienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f62d5a468e3730ec4f636d57cb9d0c6c3973a8d3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="ebadb-102">Verwenden von Interop mit dem External Data Exchange-Dienst</span><span class="sxs-lookup"><span data-stu-id="ebadb-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="ebadb-103">Mit der <xref:System.Activities.Statements.Interop>-Aktivität können Aktivitäten aus [!INCLUDE[wf](../../../../includes/wf-md.md)] in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) sowie Workflows aus [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebadb-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from [!INCLUDE[wf](../../../../includes/wf-md.md)] in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="ebadb-104">In diesem Beispiel wird veranschaulicht, wie ein WF3-Workflow, der <xref:System.Workflow.Activities.ExternalDataExchangeService> (sowie entsprechende benutzerdefinierte Aktivitäten zum Aufrufen von Methoden und Behandeln von Ereignissen) verwendet, mit der <xref:System.Activities.Statements.Interop>-Aktivität in einem WF4-Workflowdienst konfiguriert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebadb-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ebadb-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ebadb-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ebadb-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ebadb-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ebadb-107">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ebadb-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ebadb-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ebadb-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ebadb-109">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebadb-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="ebadb-110">Öffnen Sie die Datei ExternalDataExchange.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebadb-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ebadb-111">Drücken Sie STRG+UMSCHALT+B, um das Beispiel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebadb-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ebadb-112">Drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebadb-112">To run the sample, press F5.</span></span>
