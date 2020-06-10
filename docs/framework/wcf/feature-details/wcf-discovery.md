---
title: WCF-Suche
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 63c6589cb2ecff9f0a5e7c8bb61b454f6516c98c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600178"
---
# <a name="wcf-discovery"></a><span data-ttu-id="d23af-102">WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="d23af-102">WCF Discovery</span></span>
<span data-ttu-id="d23af-103">Windows Communication Foundation (WCF) bietet Unterstützung, damit Dienste zur Laufzeit auf interoperable Weise erkennbar sind, indem das WS-Discovery-Protokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d23af-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="d23af-104">WCF-Dienste können Ihre Verfügbarkeit im Netzwerk mit einer Multicast Nachricht oder einem suchproxyserver ankündigen.</span><span class="sxs-lookup"><span data-stu-id="d23af-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="d23af-105">Clientanwendungen können ein Netzwerk oder einen Suchproxyserver durchsuchen, um Dienste zu ermitteln, die eine bestimmte Gruppe von Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d23af-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="d23af-106">Die Themen in diesem Abschnitt enthalten eine Übersicht, und das Programmiermodell für diese Funktion wird ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d23af-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d23af-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d23af-107">In This Section</span></span>  
 [<span data-ttu-id="d23af-108">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="d23af-108">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)  
 <span data-ttu-id="d23af-109">Bietet einen Überblick über die von WCF bereitgestellte WS-Discovery-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="d23af-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="d23af-110">Objektmodell der WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="d23af-110">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)  
 <span data-ttu-id="d23af-111">Beschreibt die Klassen im Objektmodell und die Erweiterbarkeit der WS-Discovery-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="d23af-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="d23af-112">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client</span><span class="sxs-lookup"><span data-stu-id="d23af-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="d23af-113">Zeigt, wie Sie einen Windows Communication Foundation (WCF)-Dienst auffindbar machen.</span><span class="sxs-lookup"><span data-stu-id="d23af-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="d23af-114">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="d23af-114">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)  
 <span data-ttu-id="d23af-115">Beschreibt die Schritte, die erforderlich sind, um Folgendes zu implementieren: einen Suchproxy, einen erkennbaren Dienst, der sich beim Suchproxy registriert, und einen Client, der den Suchproxy zum Suchen nach dem erkennbaren Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="d23af-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="d23af-116">Versionskontrolle für die Suche</span><span class="sxs-lookup"><span data-stu-id="d23af-116">Discovery Versioning</span></span>](discovery-versioning.md)  
 <span data-ttu-id="d23af-117">Bietet eine kurze Übersicht über eine Prototypimplementierung einiger neuer Suchfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d23af-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="d23af-118">Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.</span><span class="sxs-lookup"><span data-stu-id="d23af-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="d23af-119">Konfigurieren der Suche in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d23af-119">Configuring Discovery in a Configuration File</span></span>](configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="d23af-120">Beschreibt, wie Sie die Suche in der Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d23af-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="d23af-121">Verwenden des Suchclientchannels</span><span class="sxs-lookup"><span data-stu-id="d23af-121">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)  
 <span data-ttu-id="d23af-122">Zeigt, wie ein Discovery-Clientchannel beim Schreiben einer WCF-Client Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d23af-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
