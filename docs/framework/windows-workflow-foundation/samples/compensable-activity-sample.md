---
title: Kompensierbare Aktivität – Beispiel
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 3bf1d120cd700830a98f53495f7e9989ffec73db
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44131376"
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="4ae88-102">Kompensierbare Aktivität – Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ae88-102">Compensable Activity Sample</span></span>
<span data-ttu-id="4ae88-103">In diesem Beispiel wird veranschaulicht, wie die `CompensableActivity`-Aktivität verwendet wird, um die Arbeit zu definieren, die für eine angegebene Aktion während der normalen Ausführung erledigt werden soll, und die Arbeit, die erledigt werden muss, um diese Aktion auszugleichen, falls zu einem späteren Zeitpunkt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4ae88-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="4ae88-104">Der erste Teil des Beispiels zeigt, wie Einheiten kompensierbarer Arbeit in Windows Workflow Foundation (WF) definiert werden können mithilfe einer `CompensableActivity` Aktivität und wie sie bei einer erfolgreichen Ausführung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4ae88-104">The first part of the sample shows how units of compensable work can be defined in Windows Workflow Foundation (WF) using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="4ae88-105">Der zweite Teil des Beispiels zeigt, wie die gleichen Einheiten kompensierbarer Arbeit die Kompensation automatisch vornehmen, wenn ein unerwartetes Ereignis eintritt und die Workflowinstanz abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="4ae88-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4ae88-106">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="4ae88-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4ae88-107">Öffnen Sie mit Visual Studio 2010 die Datei "CompensableActivity.sln".</span><span class="sxs-lookup"><span data-stu-id="4ae88-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="4ae88-108">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="4ae88-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4ae88-109">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4ae88-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ae88-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="4ae88-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4ae88-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="4ae88-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4ae88-112">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4ae88-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4ae88-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4ae88-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`