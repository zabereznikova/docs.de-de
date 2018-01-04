---
title: Inhaltsbasierte Korrelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971636df3393adda96dff779c1533969f67bf57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="content-based-correlation"></a><span data-ttu-id="ff442-102">Inhaltsbasierte Korrelation</span><span class="sxs-lookup"><span data-stu-id="ff442-102">Content-Based Correlation</span></span>
<span data-ttu-id="ff442-103">Dieses Beispiel veranschaulicht, wie die Messagingaktivitäten (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>) mit mehreren inhaltsbasierten Korrelationen und einer inhaltsbasierter Korrelation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ff442-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>) can be used with multiple content-based correlations.and content-based correlation.</span></span> <span data-ttu-id="ff442-104">In diesem Szenario wird zuerst auf Grundlage einer Bestellungs-ID eine Korrelation initialisiert, und dann wird auf Grundlage der Kunden-ID später eine andere Korrelation erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff442-104">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span> <span data-ttu-id="ff442-105">Dies zeigt, wie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität basierend auf der gleichen eingehenden Nachricht einer vorhandenen Korrelation folgen und eine neue Korrelation initialisieren kann.</span><span class="sxs-lookup"><span data-stu-id="ff442-105">This shows how a <xref:System.ServiceModel.Activities.Receive> activity can both follow an existing correlation and initialize a new correlation based on the same incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ff442-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="ff442-106">Demonstrates</span></span>  
 <span data-ttu-id="ff442-107">Messagingaktivitäten und inhaltsbasierte Korrelation</span><span class="sxs-lookup"><span data-stu-id="ff442-107">Messaging activities and content-based correlation</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ff442-108">Diskussion</span><span class="sxs-lookup"><span data-stu-id="ff442-108">Discussion</span></span>  
 <span data-ttu-id="ff442-109">In diesem Beispiel wird gezeigt, wie mehrere inhaltsbasierte Korrelationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff442-109">This sample shows how to use multiple content-based correlations.</span></span>  <span data-ttu-id="ff442-110">In diesem Szenario wird zuerst auf Grundlage einer Bestellungs-ID eine Korrelation initialisiert, und dann wird auf Grundlage der Kunden-ID später eine andere Korrelation erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff442-110">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span>  <span data-ttu-id="ff442-111">Die Korrelationen überlappen mithilfe einer <xref:System.ServiceModel.Activities.Receive>-Aktivität, die auf Grundlage der gleichen eingehenden Nachricht einer vorhandenen Korrelation (PurchaseOrderId) folgt und eine neue Korrelation (CustomerId) initialisiert.</span><span class="sxs-lookup"><span data-stu-id="ff442-111">The correlations are cascaded using a <xref:System.ServiceModel.Activities.Receive> activity that both follows an existing correlation (PurchaseOrderId) and initializes a new correlation (CustomerId) based on the same incoming message.</span></span>  <span data-ttu-id="ff442-112">Die <xref:System.ServiceModel.Activities.Receive>-Aktivität erreicht dies mithilfe der Eigenschaften <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> und <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff442-112">To accomplish this, the <xref:System.ServiceModel.Activities.Receive> activity uses the <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> and <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="ff442-113">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff442-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="ff442-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ff442-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ff442-115">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "CascadingCorrelation.sln".</span><span class="sxs-lookup"><span data-stu-id="ff442-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CascadingCorrelation.sln solution file.</span></span>  
  
3.  <span data-ttu-id="ff442-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff442-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="ff442-117">Drücken Sie F5, um den Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ff442-117">To run the server, press F5.</span></span>  
  
5.  <span data-ttu-id="ff442-118">Sobald der Dienst bereit ist und Nachrichten überwacht, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Clientprojekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="ff442-118">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff442-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ff442-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ff442-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ff442-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ff442-121">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ff442-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ff442-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ff442-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`