---
title: Ermitteln eines Diensts mit UniqueListenUriMode (Beispiel)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82f47fb0b789e41c332ebae2cfeaeb350ff0fddd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="2a986-102">Ermitteln eines Diensts mit UniqueListenUriMode (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="2a986-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="2a986-103">In diesem Beispiel wird veranschaulicht, wie ein Dienst ermittelt wird, dessen <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.ListenUriMode.Unique> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2a986-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="2a986-104">Wenn die <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.ListenUriMode.Unique> festgelegt ist, wird die Eindeutigkeit des ListenUri sichergestellt, indem entweder der Port eindeutig festgelegt wird oder der Pfad durch Anhängen einer GUID eindeutig festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2a986-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="2a986-105">Funktionen des Diensts</span><span class="sxs-lookup"><span data-stu-id="2a986-105">Features on the Service</span></span>  
 <span data-ttu-id="2a986-106">Die <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A>-Eigenschaft wird für den TCP-Endpunkt auf <xref:System.ServiceModel.Description.ListenUriMode.Unique> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a986-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="2a986-107">Der Dienst wird dann über eine <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Endpunkt ermittelbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="2a986-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="2a986-108">Funktionen des Clients</span><span class="sxs-lookup"><span data-stu-id="2a986-108">Features on the Client</span></span>  
 <span data-ttu-id="2a986-109">Dieser Client stellt mithilfe der `Via.Uri`-Methode eine Verbindung mit dem Dienst mit dem richtigen <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> her.</span><span class="sxs-lookup"><span data-stu-id="2a986-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="2a986-110">Es wird dann eine Abfrage an die von der Methode zurückgegebenen <xref:System.ServiceModel.Discovery.FindResponse> gesendet, ob ein gültiger <xref:System.ServiceModel.Endpoint.ListenUri%2A> darin enthalten ist und dieser sich vom `Address.Uri` unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2a986-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="2a986-111">Die entsprechenden Informationen werden dann an die `InvokeCalculatorService`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="2a986-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="2a986-112">In der `InvokeCalculatorService`-Methode wurde der <xref:System.ServiceModel.Endpoint.ListenUri%2A> vom Aufrufer übergeben. Danach wird dem Clientendpunkt ein `ClientViaBehavior` mit dem richtigen `Via.Uri` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2a986-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="2a986-113">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a986-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="2a986-114">Öffnen Sie UniqueListenUriMode.sln mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a986-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="2a986-115">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2a986-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2a986-116">Führen Sie die Dienstanwendung aus, die im Ordner [Projektmappenbasisverzeichnis]\service\bin\debug generiert wird.</span><span class="sxs-lookup"><span data-stu-id="2a986-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="2a986-117">Führen Sie die Clientanwendung aus, die im Ordner [Projektmappenbasisverzeichnis]\Client\bin\debug generiert wird.</span><span class="sxs-lookup"><span data-stu-id="2a986-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="2a986-118">Der Client sucht den ausgeführten Dienst und schreibt die vom Endpunkt des Diensts veröffentlichten Metadaten in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="2a986-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a986-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2a986-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a986-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2a986-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a986-121">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2a986-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a986-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2a986-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="2a986-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a986-123">See Also</span></span>
