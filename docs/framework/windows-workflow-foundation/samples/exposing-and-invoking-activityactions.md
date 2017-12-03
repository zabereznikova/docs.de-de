---
title: "Verfügbarmachen und Aufrufen von ActivityActions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27b5ea6c4a4afea1bc3cb9f5a79d22850d2a4143
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="10d37-102">Verfügbarmachen und Aufrufen von ActivityActions</span><span class="sxs-lookup"><span data-stu-id="10d37-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="10d37-103">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität, die über eine <xref:System.Activities.ActivityAction> verfügt, entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="10d37-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="10d37-104">Darüber hinaus wird die Verwendung dieser Aktivität veranschaulicht, indem eine Implementierung der <xref:System.Activities.ActivityAction> bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="10d37-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="10d37-105">Ein <xref:System.Activities.ActivityAction> ermöglicht einem aktivitätsautor, "Löcher" mit bestimmten Signaturen, in denen der aktivitätsbenutzer ein benutzerdefiniertes Verhalten einbinden kann, verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="10d37-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="10d37-106">Z. B. die <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` Aktivität (die über eine Auflistung von Elementen wirkt) hat eine <xref:System.Activities.ActivityAction> , mit dessen Hilfe der aktivitätsbenutzer Verhalten einzubinden, das auf das aktuelle iterationselement wirkt.</span><span class="sxs-lookup"><span data-stu-id="10d37-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="10d37-107">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="10d37-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="10d37-108">Öffnen der **ActivityAction.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10d37-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="10d37-109">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="10d37-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10d37-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="10d37-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="10d37-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="10d37-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="10d37-112">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="10d37-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="10d37-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="10d37-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`