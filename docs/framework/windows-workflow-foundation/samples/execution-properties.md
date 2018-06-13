---
title: Ausführungseigenschaften
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 201fe222de1cb2029696a1694ae97815db5f913d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513021"
---
# <a name="execution-properties"></a><span data-ttu-id="07808-102">Ausführungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="07808-102">Execution Properties</span></span>
<span data-ttu-id="07808-103">Dieses Beispiel zeigt, wie in einer benutzerdefinierten Aktivität eine Ausführungseigenschaft definiert und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07808-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="07808-104">Mit der Ausführungseigenschaft in diesem Beispiel wird die Vordergrundfarbe der Konsole bestimmt.</span><span class="sxs-lookup"><span data-stu-id="07808-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="07808-105">Anhand eines Beispielworkflows wird gezeigt, wie mit verschiedenen logischen Ausführungspfaden (Verzweigungen einer <xref:System.Activities.Statements.Parallel>-Aktivität) trotz der überlappenden Ausführung von Aktivitäten (verzweigungsübergreifende Ausführung der <xref:System.Activities.Statements.Parallel>-Aktivität) unterschiedliche Konsolenfarben beibehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="07808-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="07808-106">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="07808-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="07808-107">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappe "ExecutionProperties.sln".</span><span class="sxs-lookup"><span data-stu-id="07808-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07808-108">Wenn Sie "ThreeColors.xaml" vor dem Erstellen der Projektmappe anzeigen, wird ein Fehler angezeigt, da die verwendeten benutzerdefinierten Aktivitäten zur gleichen Zeit erstellt werden müssen wie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="07808-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="07808-109">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="07808-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07808-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="07808-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="07808-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="07808-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="07808-112">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="07808-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="07808-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="07808-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`