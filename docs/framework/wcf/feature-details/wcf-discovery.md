---
title: WCF-Suche
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 176e9760d98f9640bd9d1c7b059287dc29c0d666
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289359"
---
# <a name="wcf-discovery"></a><span data-ttu-id="46b49-102">WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="46b49-102">WCF Discovery</span></span>

<span data-ttu-id="46b49-103">Windows Communication Foundation (WCF) bietet Unterstützung, damit Dienste zur Laufzeit auf interoperable Weise erkannt werden können, indem das WS-Discovery Protokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="46b49-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="46b49-104">WCF-Dienste können Ihre Verfügbarkeit im Netzwerk mit einer Multicast Nachricht oder einem suchproxyserver ankündigen.</span><span class="sxs-lookup"><span data-stu-id="46b49-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="46b49-105">Clientanwendungen können ein Netzwerk oder einen Suchproxyserver durchsuchen, um Dienste zu ermitteln, die eine bestimmte Gruppe von Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="46b49-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="46b49-106">Die Themen in diesem Abschnitt enthalten eine Übersicht, und das Programmiermodell für diese Funktion wird ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46b49-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46b49-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="46b49-107">In This Section</span></span>  

 [<span data-ttu-id="46b49-108">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="46b49-108">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)  
 <span data-ttu-id="46b49-109">Bietet einen Überblick über die von WCF bereitgestellte WS-Discovery Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="46b49-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="46b49-110">Objektmodell der WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="46b49-110">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)  
 <span data-ttu-id="46b49-111">Beschreibt die Klassen im Objektmodell und die Erweiterbarkeit der WS-Discovery-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="46b49-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="46b49-112">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client</span><span class="sxs-lookup"><span data-stu-id="46b49-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="46b49-113">Zeigt, wie Sie einen Windows Communication Foundation (WCF)-Dienst auffindbar machen.</span><span class="sxs-lookup"><span data-stu-id="46b49-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="46b49-114">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="46b49-114">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)  
 <span data-ttu-id="46b49-115">Beschreibt die Schritte, die erforderlich sind, um Folgendes zu implementieren: einen Suchproxy, einen erkennbaren Dienst, der sich beim Suchproxy registriert, und einen Client, der den Suchproxy zum Suchen nach dem erkennbaren Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="46b49-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="46b49-116">Versionskontrolle für die Suche</span><span class="sxs-lookup"><span data-stu-id="46b49-116">Discovery Versioning</span></span>](discovery-versioning.md)  
 <span data-ttu-id="46b49-117">Bietet eine kurze Übersicht über eine Prototypimplementierung einiger neuer Suchfunktionen.</span><span class="sxs-lookup"><span data-stu-id="46b49-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="46b49-118">Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.</span><span class="sxs-lookup"><span data-stu-id="46b49-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="46b49-119">Konfigurieren der Suche in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="46b49-119">Configuring Discovery in a Configuration File</span></span>](configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="46b49-120">Beschreibt, wie Sie die Suche in der Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="46b49-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="46b49-121">Verwenden des Suchclientchannels</span><span class="sxs-lookup"><span data-stu-id="46b49-121">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)  
 <span data-ttu-id="46b49-122">Zeigt, wie ein Discovery-Clientchannel beim Schreiben einer WCF-Client Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="46b49-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
