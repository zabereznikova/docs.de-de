---
title: 'Vorgehensweise: Testen des Suchproxys'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: b08e8561ceff9f0a427a9ea9acb2309772579853
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294663"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="54af4-102">Vorgehensweise: Testen des Suchproxys</span><span class="sxs-lookup"><span data-stu-id="54af4-102">How to: Test the Discovery Proxy</span></span>

<span data-ttu-id="54af4-103">Dies ist das vierte von vier Themen, in denen beschrieben wird, wie Sie einen Suchproxy implementieren.</span><span class="sxs-lookup"><span data-stu-id="54af4-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="54af4-104">Im vorherigen Thema Gewusst [wie: Implementieren einer Client Anwendung, die den suchproxy zum Suchen nach einem Dienst verwendet](client-app-discovery-proxy-to-find-a-service.md), haben Sie eine WCF-Client Anwendung implementiert, die den suchproxy zum Suchen nach einem Dienst verwendet und dann den Dienst aufruft.</span><span class="sxs-lookup"><span data-stu-id="54af4-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="54af4-105">In diesem Thema wird beschrieben, wie Sie überprüfen, ob der Suchproxy, der Dienst und die Clientanwendung ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="54af4-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="54af4-106">Ausführen des Suchproxys</span><span class="sxs-lookup"><span data-stu-id="54af4-106">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="54af4-107">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="54af4-107">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="54af4-108">Ggf. wird ein Dialogfeld mit folgendem Hinweis angezeigt: Die Windows-Firewall hat einige Funktionen dieses Programms geblockt.</span><span class="sxs-lookup"><span data-stu-id="54af4-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="54af4-109">Wenn diese Meldung angezeigt wird, klicken Sie auf die Schaltfläche **Sperre entsperren** .</span><span class="sxs-lookup"><span data-stu-id="54af4-109">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="54af4-110">Führen Sie innerhalb der Eingabeaufforderung den Suchproxy "DiscoveryProxy.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="54af4-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="54af4-111">Die Anwendung sollte den folgenden Text anzeigen: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="54af4-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="54af4-112">Ausführen des erkennbaren Diensts</span><span class="sxs-lookup"><span data-stu-id="54af4-112">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="54af4-113">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="54af4-113">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="54af4-114">Führen Sie innerhalb der Eingabeaufforderung den erkennbaren Dienst "Service.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="54af4-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="54af4-115">Der DiscoveryProxy.exe sollte den folgenden Text anzeigen: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="54af4-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="54af4-116">Ausführen der Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="54af4-116">Run the Client Application</span></span>  
  
1. <span data-ttu-id="54af4-117">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="54af4-117">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="54af4-118">Führen Sie innerhalb der Eingabeaufforderung die Anwendung "client.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="54af4-118">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="54af4-119">Nach einigen Sekunden zeigt die Clientanwendung den folgenden Text an: Verbindung mit [Dienstendpunkt] wird hergestellt.</span><span class="sxs-lookup"><span data-stu-id="54af4-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="54af4-120">"service.exe" sollte dann den folgenden Text anzeigen: Begrüßungsanforderung empfangen, Antwort folgt.</span><span class="sxs-lookup"><span data-stu-id="54af4-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="54af4-121">"client.exe" zeigt dann den folgenden Text an: Hello Client!</span><span class="sxs-lookup"><span data-stu-id="54af4-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="54af4-122">Herunterfahren der Anwendungen</span><span class="sxs-lookup"><span data-stu-id="54af4-122">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="54af4-123">Fahren Sie die Clientanwendung herunter.</span><span class="sxs-lookup"><span data-stu-id="54af4-123">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="54af4-124">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="54af4-124">Shut down the service.</span></span> <span data-ttu-id="54af4-125">Der Suchproxy zeigt den folgenden Text an: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="54af4-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="54af4-126">Fahren Sie den Suchproxy herunter.</span><span class="sxs-lookup"><span data-stu-id="54af4-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54af4-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54af4-127">See also</span></span>

- [<span data-ttu-id="54af4-128">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="54af4-128">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="54af4-129">Vorgehensweise: Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="54af4-129">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="54af4-130">Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert ist</span><span class="sxs-lookup"><span data-stu-id="54af4-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="54af4-131">Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet</span><span class="sxs-lookup"><span data-stu-id="54af4-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
