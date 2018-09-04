---
title: Suchrouterdienst
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 9c0c409eb6cf3146a198b9f4bcd6d76660f5da36
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509080"
---
# <a name="discovery-router-service"></a><span data-ttu-id="0e22f-102">Suchrouterdienst</span><span class="sxs-lookup"><span data-stu-id="0e22f-102">Discovery Router Service</span></span>
<span data-ttu-id="0e22f-103">In diesem Beispiel wird veranschaulicht, wie Suchnachrichten an einen anderen Endpunkt weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0e22f-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="0e22f-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="0e22f-104">Demonstrates</span></span>  
 <span data-ttu-id="0e22f-105">Suchrouting</span><span class="sxs-lookup"><span data-stu-id="0e22f-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="0e22f-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="0e22f-106">Discussion</span></span>  
 <span data-ttu-id="0e22f-107">Suchrouting ist in einem Szenario nützlich, in dem ein Client mit einem Proxy nach einem Dienst sucht und dieser Dienst für den Proxy nicht verfügbar ist, der Proxy jedoch einen anderen Proxy kennt.</span><span class="sxs-lookup"><span data-stu-id="0e22f-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="0e22f-108">Dieser Proxy kann das Suchpaket vom Client an den zweiten Proxy weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="0e22f-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="0e22f-109">Der zweite Proxy kann nach dem Dienst suchen und die Antworten an den ursprünglichen Client zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0e22f-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="0e22f-110">In diesem Beispiel sendet ein Client eine Nachricht an eine Suchroutingkomponente.</span><span class="sxs-lookup"><span data-stu-id="0e22f-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="0e22f-111">Diese Nachricht wird an einen bestimmten Endpunkt des Suchrouters gesendet.</span><span class="sxs-lookup"><span data-stu-id="0e22f-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="0e22f-112">Der Router leitet die Nachricht dann an einen UDP-Multicastendpunkt weiter.</span><span class="sxs-lookup"><span data-stu-id="0e22f-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="0e22f-113">Die Überprüfungsnachricht wird an den Multicastendpunkt gesendet, und ein Dienst, der eine UDP-Multicastadresse überwacht, reagiert auf diesen Suchrouter.</span><span class="sxs-lookup"><span data-stu-id="0e22f-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="0e22f-114">Der Suchrouter sammelt die Antworten und sendet sie an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="0e22f-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0e22f-115">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0e22f-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0e22f-116">Erstellen Sie das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0e22f-116">Build the sample.</span></span>  
  
2.  <span data-ttu-id="0e22f-117">Führen Sie die ausführbare DiscoveryRouter-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="0e22f-117">Run the DiscoveryRouter executable.</span></span>  
  
3.  <span data-ttu-id="0e22f-118">Führen Sie die ausführbare Dienstdatei aus dem Buildverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="0e22f-118">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="0e22f-119">Führen Sie die ausführbare Clientanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="0e22f-119">Run the client executable.</span></span> <span data-ttu-id="0e22f-120">Beachten Sie, dass der Client den Dienst sucht.</span><span class="sxs-lookup"><span data-stu-id="0e22f-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e22f-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0e22f-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0e22f-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0e22f-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0e22f-123">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0e22f-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e22f-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0e22f-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
