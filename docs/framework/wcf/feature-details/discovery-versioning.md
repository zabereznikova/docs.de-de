---
title: Versionskontrolle für die Suche
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 18c160e5e08ed9b6733bed9d5e40a4dde00dfd1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489179"
---
# <a name="discovery-versioning"></a><span data-ttu-id="fd73e-102">Versionskontrolle für die Suche</span><span class="sxs-lookup"><span data-stu-id="fd73e-102">Discovery Versioning</span></span>
<span data-ttu-id="fd73e-103">Dieses Thema enthält eine kurze Übersicht über die Implementierung einiger neuer Suchfunktionen.</span><span class="sxs-lookup"><span data-stu-id="fd73e-103">This topic provides a brief overview of the implementation of some new discovery features.</span></span> <span data-ttu-id="fd73e-104">Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.</span><span class="sxs-lookup"><span data-stu-id="fd73e-104">It also gives an overview on how to select the discovery version to use.</span></span>  
  
## <a name="discovery-versioning"></a><span data-ttu-id="fd73e-105">Versionskontrolle für die Suche</span><span class="sxs-lookup"><span data-stu-id="fd73e-105">Discovery Versioning</span></span>  
 <span data-ttu-id="fd73e-106">Die Suchfunktion verfügt über die Unterstützung für drei Versionen des WS_Discovery-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="fd73e-106">The discovery feature includes support for three versions of the WS_Discovery protocol.</span></span> <span data-ttu-id="fd73e-107">Mithilfe der Such-APIs können Sie auswählen, welche Version des Protokolls Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fd73e-107">The discovery APIs allow you to select which version of the protocol you want to use.</span></span> <span data-ttu-id="fd73e-108">In diesem Dokument werden die Einstellungen zur Versionskontrolle kurz beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd73e-108">This document briefly describes the versioning-related settings.</span></span>  
  
 <span data-ttu-id="fd73e-109">Die folgenden Discovery-Klassen verfügen jetzt über eine <xref:System.ServiceModel.Discovery.DiscoveryVersion>-Eigenschaft und verwenden in ihren Konstruktoren ein <xref:System.ServiceModel.Discovery.DiscoveryVersion>-Argument:</span><span class="sxs-lookup"><span data-stu-id="fd73e-109">The following Discovery classes now have a <xref:System.ServiceModel.Discovery.DiscoveryVersion> property and take a <xref:System.ServiceModel.Discovery.DiscoveryVersion> argument in their constructors:</span></span>  
  
-   <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
### <a name="discoveryversionwsdiscoveryapril2005"></a><span data-ttu-id="fd73e-110">DiscoveryVersion.WSDiscoveryApril2005</span><span class="sxs-lookup"><span data-stu-id="fd73e-110">DiscoveryVersion.WSDiscoveryApril2005</span></span>  
 <span data-ttu-id="fd73e-111">Bereitstellen von <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> als Konstruktor Parameter stellt die Implementierung die Version "April2005" des WS-Discovery-Protokolls zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd73e-111">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> as a constructor parameter makes the implementation use the April2005 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="fd73e-112">Diese Version entspricht der veröffentlichten Version der WS-Discovery-Protokollspezifikation.</span><span class="sxs-lookup"><span data-stu-id="fd73e-112">This version corresponds to the published version of the WS-Discovery protocol specification.</span></span> <span data-ttu-id="fd73e-113">Sie sollten diese Version bei Interaktionen mit älteren Anwendungen verwenden, die die Version "April2005" der WS-Suche nutzen.</span><span class="sxs-lookup"><span data-stu-id="fd73e-113">This version should be used to interoperate with legacy application utilizing the April2005 version of WS-Discovery.</span></span>  
  
### <a name="discoveryversionwsdiscovery11"></a><span data-ttu-id="fd73e-114">DiscoveryVersion.WSDiscovery11</span><span class="sxs-lookup"><span data-stu-id="fd73e-114">DiscoveryVersion.WSDiscovery11</span></span>  
 <span data-ttu-id="fd73e-115">Die von den APIs verwendete standardsuchversion ist <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span><span class="sxs-lookup"><span data-stu-id="fd73e-115">The default discovery version used by the APIs is <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span></span> <span data-ttu-id="fd73e-116">Dies ist die momentane Standardversion des WS-Discovery-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="fd73e-116">This is the current standardized version of the WS-Discovery protocol.</span></span>  
  
## <a name="discoveryversionwsdiscoverycd1"></a><span data-ttu-id="fd73e-117">DiscoveryVersion.WSDiscoveryCD1</span><span class="sxs-lookup"><span data-stu-id="fd73e-117">DiscoveryVersion.WSDiscoveryCD1</span></span>  
 <span data-ttu-id="fd73e-118">Das Bereitstellen von <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> als Konstruktorparameter führt dazu, dass die Implementierung die Version "Committee Draft 1" des WS-Discovery-Protokolls verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd73e-118">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> as a constructor parameter makes the implementation use the committee draft 1 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="fd73e-119">Sie sollten diese Version des Protokolls bei Interaktionen mit Implementierungen verwenden, die die CD1-Version des WS-Discovery-Protokolls nutzen.</span><span class="sxs-lookup"><span data-stu-id="fd73e-119">This version of the protocol should be used to interoperate with implementations running the CD1 version of the WS-Discovery protocol.</span></span>  
  
## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a><span data-ttu-id="fd73e-120">Unterstützen von mehreren UDP-Suchendpunkten für verschiedene Suchversionen auf einem einzelnen Diensthost</span><span class="sxs-lookup"><span data-stu-id="fd73e-120">Supporting Multiple UDP Discovery Endpoints for Different Discovery Versions on a Single Service Host</span></span>  
 <span data-ttu-id="fd73e-121">Es kann erforderlich sein, auf einem einzelnen Diensthost mehrere UDP-Suchendpunkte für verschiedene Suchversionen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="fd73e-121">You may want to expose multiple UDP Discovery Endpoints for different discovery versions on a single service host.</span></span> <span data-ttu-id="fd73e-122">Dazu müssen Sie eine eindeutige Adresse für jeden UDP-Suchendpunkt angeben.</span><span class="sxs-lookup"><span data-stu-id="fd73e-122">To do this you must specify a unique address for each UDP discovery endpoint.</span></span> <span data-ttu-id="fd73e-123">Das folgende Beispiel zeigt die dazu erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="fd73e-123">The following example shows how to do this.</span></span>  
  
```  
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);  
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
  
newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");  
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionAril2005");  
  
serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);  
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);  
```
