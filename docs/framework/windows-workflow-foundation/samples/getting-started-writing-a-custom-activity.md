---
title: "Erste Schritte zum Schreiben einer benutzerdefinierten Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0cf8bd0368977b665f2ea412e4debbc1f681e5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="d55d4-102">Erste Schritte zum Schreiben einer benutzerdefinierten Aktivität</span><span class="sxs-lookup"><span data-stu-id="d55d4-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="d55d4-103">In diesem Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Aktivität in XAML definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d55d4-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="d55d4-104">Der Aktivität wird der Name `Rhyme` zugewiesen, und ihre Logik ist eine Sequenz von drei <xref:System.Activities.Statements.WriteLine>-Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="d55d4-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d55d4-105">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d55d4-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d55d4-106">Öffnen der **Simple.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d55d4-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d55d4-107">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d55d4-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d55d4-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d55d4-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d55d4-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d55d4-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d55d4-110">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d55d4-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d55d4-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d55d4-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`