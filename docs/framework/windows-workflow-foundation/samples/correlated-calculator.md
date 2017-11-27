---
title: Korrelierter Rechner
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d0d3c03b946a1f3805ea6e229e4019540b58286
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="correlated-calculator"></a><span data-ttu-id="af397-102">Korrelierter Rechner</span><span class="sxs-lookup"><span data-stu-id="af397-102">Correlated Calculator</span></span>
<span data-ttu-id="af397-103">In diesem Beispiel wird veranschaulicht, wie die Messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>) im Designer auf Grundlage eines Parameters in der Meldung mit inhaltsbasierter Korrelation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af397-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="af397-104">In diesem Szenario befinden sich die Vorgänge des Rechners in einem parallelen Konvoi.</span><span class="sxs-lookup"><span data-stu-id="af397-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="af397-105">Sowohl eine Instanz als auch eine Korrelation (basierend auf `CalculatorId`) werden erstellt, wenn die erste Meldung an den Workflow gesendet wird; nachfolgende Meldungen mit derselben `CalculatorId` werden an diese Instanz weitergeleitet, bis der Reset-Vorgang aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="af397-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="af397-106">Der Client wird als WPF-Anwendung implementiert, die einen codebasierten Clientproxy verwendet, um mit dem Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="af397-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="af397-107">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="af397-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="af397-108">Starten Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erhöhten Rechten, und öffnen Sie die Projektmappendatei "For.sln".</span><span class="sxs-lookup"><span data-stu-id="af397-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="af397-109">Navigieren Sie zu dem Ordner, der [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] enthält.</span><span class="sxs-lookup"><span data-stu-id="af397-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="af397-110">Mit der rechten Maustaste Devenv.exe aus, und wählen Sie **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="af397-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="af397-111">Öffnen Sie die Projektmappendatei " CorrelatedCalculator.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af397-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="af397-112">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af397-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="af397-113">Drücken Sie STRG+F5, um das Dienstprojekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af397-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="af397-114">Sobald der Dienst bereit ist und Nachrichten überwacht, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Clientprojekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="af397-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af397-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="af397-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="af397-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="af397-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="af397-117">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="af397-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="af397-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="af397-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`  
  
## <a name="see-also"></a><span data-ttu-id="af397-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af397-119">See Also</span></span>
