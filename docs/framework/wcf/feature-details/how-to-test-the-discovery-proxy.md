---
title: 'Vorgehensweise: Testen des Suchproxys'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 35edbd03e912ae2d9c491afb28dee1c4a3055d14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491221"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="6d5bb-102">Vorgehensweise: Testen des Suchproxys</span><span class="sxs-lookup"><span data-stu-id="6d5bb-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="6d5bb-103">Dies ist das vierte von vier Themen, in denen beschrieben wird, wie Sie einen Suchproxy implementieren.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="6d5bb-104">Im vorherigen Thema [wie: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), Sie eine WCF-Clientanwendung, die den suchproxy zum Suchen nach einem Dienst verwendet und ruft dann den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="6d5bb-105">In diesem Thema wird beschrieben, wie Sie überprüfen, ob der Suchproxy, der Dienst und die Clientanwendung ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="6d5bb-106">Ausführen des Suchproxys</span><span class="sxs-lookup"><span data-stu-id="6d5bb-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="6d5bb-107">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="6d5bb-108">Ggf. wird ein Dialogfeld mit folgendem Hinweis angezeigt: Die Windows-Firewall hat einige Funktionen dieses Programms geblockt.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="6d5bb-109">Wenn Sie diese Meldung angezeigt wird, klicken Sie auf die **zum Aufheben der Sperre** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="6d5bb-110">Führen Sie innerhalb der Eingabeaufforderung den Suchproxy "DiscoveryProxy.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="6d5bb-111">Die Anwendung sollte den folgenden Text anzeigen: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="6d5bb-112">Ausführen des erkennbaren Diensts</span><span class="sxs-lookup"><span data-stu-id="6d5bb-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="6d5bb-113">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="6d5bb-114">Führen Sie innerhalb der Eingabeaufforderung den erkennbaren Dienst "Service.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="6d5bb-115">Die DiscoveryProxy.exe sollte den folgenden Text anzeigen: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="6d5bb-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="6d5bb-116">Ausführen der Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="6d5bb-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="6d5bb-117">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="6d5bb-118">Führen Sie innerhalb der Eingabeaufforderung die Anwendung "client.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="6d5bb-119">Nach einigen Sekunden zeigt die Clientanwendung den folgenden Text an: Verbindung mit [Dienstendpunkt] wird hergestellt.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="6d5bb-120">"service.exe" sollte dann den folgenden Text anzeigen: Begrüßungsanforderung empfangen, Antwort folgt.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="6d5bb-121">"client.exe" zeigt dann den folgenden Text an: Hello Client!</span><span class="sxs-lookup"><span data-stu-id="6d5bb-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="6d5bb-122">Herunterfahren der Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6d5bb-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="6d5bb-123">Fahren Sie die Clientanwendung herunter.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="6d5bb-124">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-124">Shut down the service.</span></span> <span data-ttu-id="6d5bb-125">Der Suchproxy zeigt den folgenden Text an: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="6d5bb-126">Fahren Sie den Suchproxy herunter.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5bb-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d5bb-127">See Also</span></span>  
 [<span data-ttu-id="6d5bb-128">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="6d5bb-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="6d5bb-129">Vorgehensweise: Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="6d5bb-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [<span data-ttu-id="6d5bb-130">Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert ist</span><span class="sxs-lookup"><span data-stu-id="6d5bb-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [<span data-ttu-id="6d5bb-131">Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet</span><span class="sxs-lookup"><span data-stu-id="6d5bb-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
