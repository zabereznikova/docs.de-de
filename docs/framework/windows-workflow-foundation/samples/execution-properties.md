---
title: "Ausführungseigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fed33544654e6929997567198c0f07346e715d1e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="execution-properties"></a><span data-ttu-id="a4e1c-102">Ausführungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="a4e1c-102">Execution Properties</span></span>
<span data-ttu-id="a4e1c-103">Dieses Beispiel zeigt, wie in einer benutzerdefinierten Aktivität eine Ausführungseigenschaft definiert und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="a4e1c-104">Mit der Ausführungseigenschaft in diesem Beispiel wird die Vordergrundfarbe der Konsole bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="a4e1c-105">Anhand eines Beispielworkflows wird gezeigt, wie mit verschiedenen logischen Ausführungspfaden (Verzweigungen einer <xref:System.Activities.Statements.Parallel>-Aktivität) trotz der überlappenden Ausführung von Aktivitäten (verzweigungsübergreifende Ausführung der <xref:System.Activities.Statements.Parallel>-Aktivität) unterschiedliche Konsolenfarben beibehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a4e1c-106">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a4e1c-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a4e1c-107">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappe "ExecutionProperties.sln".</span><span class="sxs-lookup"><span data-stu-id="a4e1c-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4e1c-108">Wenn Sie "ThreeColors.xaml" vor dem Erstellen der Projektmappe anzeigen, wird ein Fehler angezeigt, da die verwendeten benutzerdefinierten Aktivitäten zur gleichen Zeit erstellt werden müssen wie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="a4e1c-109">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4e1c-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4e1c-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a4e1c-112">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4e1c-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4e1c-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`