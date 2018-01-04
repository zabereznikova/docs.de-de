---
title: CustomDiscoveryMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2e13fde338075d9ef16c205efcfcb452235f0af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="d67bb-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="d67bb-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="d67bb-103">In diesem Beispiel wird gezeigt, wie benutzerdefinierte XML-Metadaten in die Suchmetadaten eines sichtbaren Endpunkts eingefügt werden, der von einem Dienst verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="d67bb-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="d67bb-104">Im Beispiel wird außerdem erläutert, wie ein Client nach dem Dienst suchen und diese benutzerdefinierten Daten extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="d67bb-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="d67bb-105">Das folgende Beispiel besteht aus zwei Projekten, Dienst und Client.</span><span class="sxs-lookup"><span data-stu-id="d67bb-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="d67bb-106">Dienst</span><span class="sxs-lookup"><span data-stu-id="d67bb-106">Service</span></span>  
 <span data-ttu-id="d67bb-107">In der `main`-Methode wird im Beispiel gezeigt, dass ein Objekt des Typs <xref:System.Xml.Linq.XElement> mit den gewünschten Feldern aufgefüllt und dem <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d67bb-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="d67bb-108">Das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> wird einem bestimmten Endpunkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d67bb-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="d67bb-109">Wenn nach diesem Endpunkt gesucht wird, enthalten die Suchmetadaten die benutzerdefinierten Daten, die hier hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="d67bb-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="d67bb-110">Client</span><span class="sxs-lookup"><span data-stu-id="d67bb-110">Client</span></span>  
 <span data-ttu-id="d67bb-111">Das Beispiel zeigt, dass die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode für einen <xref:System.ServiceModel.Discovery.DiscoveryClient> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d67bb-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="d67bb-112">Die entsprechende <xref:System.ServiceModel.Discovery.FindResponse> wird danach für die entsprechenden und erwarteten XML-Elemente abgefragt.</span><span class="sxs-lookup"><span data-stu-id="d67bb-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="d67bb-113">Diese Elemente werden dann in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d67bb-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d67bb-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="d67bb-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="d67bb-115">Laden Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], und erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d67bb-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="d67bb-116">Führen Sie zuerst die Dienstanwendung aus, die unter [Projektmappen-Basisverzeichnis]\service\bin\debug generiert wurde, und führen Sie danach die Clientanwendung aus, die unter [Projektmappen-Basisverzeichnis]\Client\bin\debug generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d67bb-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="d67bb-117">Beachten Sie, dass der Dienst online geschaltet wird, der Client nach dem Dienst sucht und die im Endpunkt veröffentlichten Metadaten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d67bb-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d67bb-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d67bb-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d67bb-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d67bb-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d67bb-120">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d67bb-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d67bb-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d67bb-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="d67bb-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d67bb-122">See Also</span></span>
