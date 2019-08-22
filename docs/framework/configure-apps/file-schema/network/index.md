---
title: Netzwerkeinstellungsschema
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 0f5d762a2b688bebcb7c027be6c639b6d64c069d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664110"
---
# <a name="network-settings-schema"></a><span data-ttu-id="ee0c9-102">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="ee0c9-102">Network Settings Schema</span></span>
<span data-ttu-id="ee0c9-103">Netzwerkeinstellungen geben an, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="ee0c9-104">Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<system.Net>-Elements (Netzwerkeinstellungen)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ee0c9-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="ee0c9-105">Element</span><span class="sxs-lookup"><span data-stu-id="ee0c9-105">Element</span></span>|<span data-ttu-id="ee0c9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee0c9-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee0c9-107">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-107">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="ee0c9-108">Gibt die Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="ee0c9-109">\<connectionManagement>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-109">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="ee0c9-110">Gibt die maximale Anzahl von Verbindungen mit Internethosts an.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="ee0c9-111">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-111">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="ee0c9-112">Gibt den Proxyserver an, der für HTTP-Anforderungen an das Internet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="ee0c9-113">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-113">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="ee0c9-114">Enthält Einstellungen für E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="ee0c9-115">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-115">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="ee0c9-116">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-116">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="ee0c9-117">\<webRequestModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-117">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="ee0c9-118">Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-118">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="ee0c9-119">URI-Einstellungen geben an, wie .NET Framework Webadressen behandelt, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-119">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="ee0c9-120">Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<Uri>-Elements (Netzwerkeinstellungen)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ee0c9-120">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="ee0c9-121">Element</span><span class="sxs-lookup"><span data-stu-id="ee0c9-121">Element</span></span>|<span data-ttu-id="ee0c9-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee0c9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee0c9-123">\<idn>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-123">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="ee0c9-124">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-124">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="ee0c9-125">\<iriParsing>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-125">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="ee0c9-126">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-126">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="ee0c9-127">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-127">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="ee0c9-128">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-128">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee0c9-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee0c9-129">See also</span></span>

- [<span data-ttu-id="ee0c9-130">Konfigurieren von Internetanwendungen</span><span class="sxs-lookup"><span data-stu-id="ee0c9-130">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="ee0c9-131">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ee0c9-131">Configuration File Schema</span></span>](../index.md)
