---
title: Erste Schritte zum Schreiben einer benutzerdefinierten Aktivität
ms.date: 03/30/2017
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
ms.openlocfilehash: 4d9c140ca230750ca1119b33252b1edb8796d458
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776657"
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="62cc1-102">Erste Schritte zum Schreiben einer benutzerdefinierten Aktivität</span><span class="sxs-lookup"><span data-stu-id="62cc1-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="62cc1-103">In diesem Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Aktivität in XAML definiert wird.</span><span class="sxs-lookup"><span data-stu-id="62cc1-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="62cc1-104">Der Aktivität wird der Name `Rhyme` zugewiesen, und ihre Logik ist eine Sequenz von drei <xref:System.Activities.Statements.WriteLine>-Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="62cc1-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="62cc1-105">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="62cc1-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="62cc1-106">Öffnen der **Simple.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62cc1-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="62cc1-107">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="62cc1-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="62cc1-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="62cc1-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="62cc1-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="62cc1-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="62cc1-110">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="62cc1-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="62cc1-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="62cc1-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`