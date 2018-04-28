---
title: Kompensierbare Aktivität – Beispiel
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba81d0eb32305e8ea099a291bef612639915292f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="7eb2a-102">Kompensierbare Aktivität – Beispiel</span><span class="sxs-lookup"><span data-stu-id="7eb2a-102">Compensable Activity Sample</span></span>
<span data-ttu-id="7eb2a-103">In diesem Beispiel wird veranschaulicht, wie die `CompensableActivity`-Aktivität verwendet wird, um die Arbeit zu definieren, die für eine angegebene Aktion während der normalen Ausführung erledigt werden soll, und die Arbeit, die erledigt werden muss, um diese Aktion auszugleichen, falls zu einem späteren Zeitpunkt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="7eb2a-104">Der erste Teil des Beispiels wird gezeigt, wie Einheiten kompensierbarer Arbeit in Windows Workflow Foundation (WF) definiert werden können mithilfe einer `CompensableActivity` Aktivität und wie sie bei einer erfolgreichen Ausführung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-104">The first part of the sample shows how units of compensable work can be defined in Windows Workflow Foundation (WF) using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="7eb2a-105">Der zweite Teil des Beispiels zeigt, wie die gleichen Einheiten kompensierbarer Arbeit die Kompensation automatisch vornehmen, wenn ein unerwartetes Ereignis eintritt und die Workflowinstanz abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7eb2a-106">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="7eb2a-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7eb2a-107">Öffnen Sie mit Visual Studio 2010 die Datei "CompensableActivity.sln".</span><span class="sxs-lookup"><span data-stu-id="7eb2a-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="7eb2a-108">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7eb2a-109">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7eb2a-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7eb2a-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7eb2a-112">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7eb2a-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7eb2a-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`