---
title: Implementieren eines Suchproxys
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 382df95fef2108d338e4ea327da9185c856eca5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579240"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="ea7a3-102">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="ea7a3-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="ea7a3-103">In diesem Thema werden die Schritte beschrieben, die zum Implementieren eines Suchproxys erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="ea7a3-104">Ein Suchproxy ist ein eigenständiger Dienst, der ein Repository mit Diensten enthält.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="ea7a3-105">Clients können einen Suchproxy abfragen, um nach erkennbaren Diensten, die für den Proxy verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="ea7a3-106">Die Art und Weise, wie ein Proxy mit Diensten aufgefüllt wird, hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="ea7a3-107">Ein Suchproxy kann z. B. eine Verbindung zu einem vorhandenen Dienstrepository herstellen und diese Informationen erkennbar machen, ein Administrator kann einem Proxy erkennbare Dienste mithilfe einer Verwaltungs-API hinzufügen, oder ein Suchproxy kann seinen internen Cache mithilfe der Ankündigungsfunktionalität aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="ea7a3-108">Die WCF-Implementierung stellt Basisklassen bereit, mit denen problemlos ein Proxy erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="ea7a3-109">Sie können mit diesen APIs einen Suchproxy für das vorhandene Repository erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="ea7a3-110">Der hier implementierte Suchproxy gleicht allen anderen WCF-Diensten. Sie können den Suchproxy auch erkennbar machen und die Clients nach seinen Endpunkten suchen lassen.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea7a3-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ea7a3-111">In This Section</span></span>  
 [<span data-ttu-id="ea7a3-112">Vorgehensweise: Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="ea7a3-112">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="ea7a3-113">Beschreibt, wie Sie einen Suchproxy implementieren.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="ea7a3-114">Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert ist</span><span class="sxs-lookup"><span data-stu-id="ea7a3-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="ea7a3-115">Beschreibt, wie ein erkennbarer WCF-Dienst implementiert wird, der beim suchproxy registriert wird.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-115">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="ea7a3-116">Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet</span><span class="sxs-lookup"><span data-stu-id="ea7a3-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="ea7a3-117">Beschreibt, wie eine WCF-Client Anwendung implementiert wird, die den suchproxy zum Suchen nach einem Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-117">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="ea7a3-118">Vorgehensweise: Testen des Suchproxys</span><span class="sxs-lookup"><span data-stu-id="ea7a3-118">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="ea7a3-119">Beschreibt, wie Sie den Code testen, den Sie in den vorherigen drei Themen geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="ea7a3-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7a3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea7a3-120">See also</span></span>

- [<span data-ttu-id="ea7a3-121">WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="ea7a3-121">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="ea7a3-122">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client</span><span class="sxs-lookup"><span data-stu-id="ea7a3-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
