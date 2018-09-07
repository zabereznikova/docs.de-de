---
title: Verwenden von AsyncOperationContext in einem Aktivitätsbeispiel
ms.date: 03/30/2017
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
ms.openlocfilehash: 4358a364a3f7ec69b7c1c548fcf82fe494f37505
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078898"
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a><span data-ttu-id="d70cf-102">Verwenden von AsyncOperationContext in einem Aktivitätsbeispiel</span><span class="sxs-lookup"><span data-stu-id="d70cf-102">Using AsyncOperationContext in an Activity Sample</span></span>
<span data-ttu-id="d70cf-103">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Activities.CodeActivity> entwickelt wird, die <xref:System.Activities.AsyncCodeActivityContext> verwendet, um Arbeiten asynchron außerhalb des Workflows auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d70cf-103">This sample demonstrates how to develop a custom <xref:System.Activities.CodeActivity> that uses <xref:System.Activities.AsyncCodeActivityContext> to perform work asynchronously outside of the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="d70cf-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="d70cf-104">Sample Details</span></span>  
 <span data-ttu-id="d70cf-105">Die Beispielaktivität verwendet die <xref:System.IO.FileStream.BeginWrite%2A>-Methode und <xref:System.IO.FileStream.EndWrite%2A>-Methode für die <xref:System.IO.FileStream>-Klasse, um Daten asynchron in eine Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d70cf-105">The sample activity uses the <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.EndWrite%2A> methods on the <xref:System.IO.FileStream> class to asynchronously write data to a file.</span></span> <span data-ttu-id="d70cf-106">Das hier gezeigte Muster kann zur Verwendung mit anderen asynchronen Methoden angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="d70cf-106">The pattern introduced here can be adapted for use with other asynchronous methods.</span></span> <span data-ttu-id="d70cf-107">Während der asynchrone Vorgang ausgeführt wird, können andere Aktivitäten im Workflow ausgeführt werden, aber der Workflow kann nicht persistent gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d70cf-107">While the asynchronous operation is executing, other activities in the workflow can execute, but the workflow cannot be persisted.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d70cf-108">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d70cf-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d70cf-109">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappe "Async.sln".</span><span class="sxs-lookup"><span data-stu-id="d70cf-109">Open the Async.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d70cf-110">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d70cf-110">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d70cf-111">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d70cf-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d70cf-112">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d70cf-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d70cf-113">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d70cf-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d70cf-114">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d70cf-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`