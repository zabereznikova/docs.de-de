---
title: Bookmarks2
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035fadb2-49fa-4ac7-b398-daf138f66e87
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c7a1ac8848bd5eff4e79e7a5e3b058720e7a12c
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="bookmarks"></a><span data-ttu-id="0f60c-102">Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="0f60c-102">Bookmarks</span></span>
<span data-ttu-id="0f60c-103">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität geschrieben wird, die ein Lesezeichen erstellt, um externe Eingaben zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="0f60c-103">This sample demonstrates how to write a custom activity that creates a bookmark to receive external input.</span></span> <span data-ttu-id="0f60c-104">Das Beispiel umfasst auch eine Basiskonsolenanwendung, die die benutzerdefinierte Aktivität in einem Workflow verwendet und anzeigt, wie einer ausgeführten Workflowinstanz zugeordnete Lesezeichen ermittelt und fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0f60c-104">The sample also includes a basic console application that uses the custom activity in a workflow and shows how to discover and resume bookmarks associated with a running workflow instance.</span></span> <span data-ttu-id="0f60c-105">Weitere Informationen zu Lesezeichen, finden Sie unter [Lesezeichen](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="0f60c-105">For more information about bookmarks, see [Bookmarks](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0f60c-106">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0f60c-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0f60c-107">Öffnen Sie die Beispielprojektmappe "Bookmarks.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f60c-107">Open the Bookmarks.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0f60c-108">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f60c-108">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="0f60c-109">Drücken Sie STRG+F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0f60c-109">To run the sample, press CTRLl + F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0f60c-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0f60c-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0f60c-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0f60c-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0f60c-112">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0f60c-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0f60c-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f60c-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CodeBodied\Bookmarks`