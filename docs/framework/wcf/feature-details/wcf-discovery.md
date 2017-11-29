---
title: WCF-Suche
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fda50f14d9003b81f93840571b8b27f874f7730b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="5371e-102">WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="5371e-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="5371e-103">bietet eine Unterstützung dafür, dass Dienste während der Laufzeit auf interoperable Weise erkennbar sind, indem das WS-Discovery-Protokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5371e-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5371e-104">-Dienste können ihre Verfügbarkeit im Netzwerk mit einer Multicastnachricht oder für einen Suchproxyserver ankündigen.</span><span class="sxs-lookup"><span data-stu-id="5371e-104"> services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="5371e-105">Clientanwendungen können ein Netzwerk oder einen Suchproxyserver durchsuchen, um Dienste zu ermitteln, die eine bestimmte Gruppe von Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5371e-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="5371e-106">Die Themen in diesem Abschnitt enthalten eine Übersicht, und das Programmiermodell für diese Funktion wird ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5371e-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5371e-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5371e-107">In This Section</span></span>  
 [<span data-ttu-id="5371e-108">Übersicht über den WCF-Ermittlung</span><span class="sxs-lookup"><span data-stu-id="5371e-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="5371e-109">Bietet eine Übersicht über WS-Discovery-Unterstützung, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5371e-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="5371e-110">Objektmodell für WCF-Ermittlung</span><span class="sxs-lookup"><span data-stu-id="5371e-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="5371e-111">Beschreibt die Klassen im Objektmodell und die Erweiterbarkeit der WS-Discovery-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="5371e-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="5371e-112">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und Client</span><span class="sxs-lookup"><span data-stu-id="5371e-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="5371e-113">Beschreibt, wie Sie einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst erkennbar machen.</span><span class="sxs-lookup"><span data-stu-id="5371e-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="5371e-114">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="5371e-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="5371e-115">Beschreibt die Schritte, die erforderlich sind, um Folgendes zu implementieren: einen Suchproxy, einen erkennbaren Dienst, der sich beim Suchproxy registriert, und einen Client, der den Suchproxy zum Suchen nach dem erkennbaren Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="5371e-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="5371e-116">Versionskontrolle für die Suche</span><span class="sxs-lookup"><span data-stu-id="5371e-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="5371e-117">Bietet eine kurze Übersicht über eine Prototypimplementierung einiger neuer Suchfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5371e-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="5371e-118">Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.</span><span class="sxs-lookup"><span data-stu-id="5371e-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="5371e-119">Konfigurieren der Suche in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="5371e-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="5371e-120">Beschreibt, wie Sie die Suche in der Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5371e-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="5371e-121">Verwenden des Suchclientchannels</span><span class="sxs-lookup"><span data-stu-id="5371e-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="5371e-122">Beschreibt, wie Sie beim Schreiben einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientanwendung einen Suchclientkanal verwenden.</span><span class="sxs-lookup"><span data-stu-id="5371e-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
