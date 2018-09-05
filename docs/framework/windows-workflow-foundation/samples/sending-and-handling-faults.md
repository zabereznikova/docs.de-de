---
title: Senden und Behandeln von Fehlern
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 896f209e7daeeab2bb33c1fde15298aae96c8776
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43733364"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="f5ee9-102">Senden und Behandeln von Fehlern</span><span class="sxs-lookup"><span data-stu-id="f5ee9-102">Sending and Handling Faults</span></span>
<span data-ttu-id="f5ee9-103">In diesem Beispiel wird veranschaulicht, wie die <xref:System.ServiceModel.Activities.SendReply>-Messagingaktivität und <xref:System.ServiceModel.Activities.ReceiveReply>-Messagingaktivität verwendet werden, um erwartete und unerwartete Fehler zu senden und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="f5ee9-104">In diesem Szenario führt die erste Clientanforderung zu einem erwarteten Fehler, der in der <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>-Auflistung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="f5ee9-105">Die nächsten Clientanforderungen führen zu unerwarteten Fehlern, bevor die abschließende Anforderung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="f5ee9-106">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5ee9-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="f5ee9-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="f5ee9-108">Öffnen Sie die Faults.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="f5ee9-109">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="f5ee9-110">Führen Sie das Dienstprojekt aus.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="f5ee9-111">In **Projektmappen-Explorer**, mit der rechten Maustaste die `FaultService` Projekt, und wählen **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="f5ee9-112">Drücken Sie STRG+F5.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="f5ee9-113">Öffnen Sie eine andere Kopie des [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="f5ee9-114">Öffnen Sie die Faults.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="f5ee9-115">Führen Sie das Clientprojekt aus.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="f5ee9-116">In **Projektmappen-Explorer**, mit der rechten Maustaste die `FaultClient` Projekt, und wählen **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="f5ee9-117">Drücken Sie STRG+F5.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5ee9-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5ee9-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f5ee9-120">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5ee9-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f5ee9-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`