---
title: Netzwerkeinstellungsschema
description: Erfahren Sie mehr über das Schema der Netzwerkeinstellungen, die angeben, wie die .NET Framework eine Verbindung mit dem Internet herstellt und URIs behandelt.
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
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504575"
---
# <a name="network-settings-schema"></a><span data-ttu-id="13ccd-103">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="13ccd-103">Network Settings Schema</span></span>
<span data-ttu-id="13ccd-104">Netzwerkeinstellungen geben an, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="13ccd-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="13ccd-105">\<system.net>Mit den Einstellungen wird angegeben, wie die .NET Framework eine Verbindung mit dem Netzwerk herstellt.</span><span class="sxs-lookup"><span data-stu-id="13ccd-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="13ccd-106">In der folgenden Tabelle wird die Funktion der einzelnen untergeordneten Konfigurationselemente unter dem- [ \<system.Net> Element (Netzwerkeinstellungen)](system-net-element-network-settings.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13ccd-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="13ccd-107">Element</span><span class="sxs-lookup"><span data-stu-id="13ccd-107">Element</span></span>|<span data-ttu-id="13ccd-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13ccd-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13ccd-109">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="13ccd-110">Gibt die Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13ccd-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="13ccd-111">\<connectionManagement>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="13ccd-112">Gibt die maximale Anzahl von Verbindungen mit Internethosts an.</span><span class="sxs-lookup"><span data-stu-id="13ccd-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="13ccd-113">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="13ccd-114">Gibt den Proxyserver an, der für HTTP-Anforderungen an das Internet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13ccd-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="13ccd-115">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="13ccd-116">Enthält Einstellungen für E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="13ccd-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="13ccd-117">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="13ccd-118">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="13ccd-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="13ccd-119">\<webRequestModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="13ccd-120">Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13ccd-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="13ccd-121">Die \<uri> Einstellungen geben an, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="13ccd-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="13ccd-122">In der folgenden Tabelle wird die Funktion der einzelnen untergeordneten Konfigurationselemente unter dem- [ \<uri> Element (URI-Einstellungen)](uri-element-uri-settings.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13ccd-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="13ccd-123">Element</span><span class="sxs-lookup"><span data-stu-id="13ccd-123">Element</span></span>|<span data-ttu-id="13ccd-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13ccd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13ccd-125">\<idn>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="13ccd-126">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="13ccd-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="13ccd-127">\<iriParsing>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="13ccd-128">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13ccd-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="13ccd-129">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="13ccd-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="13ccd-130">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="13ccd-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13ccd-131">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="13ccd-131">See also</span></span>

- [<span data-ttu-id="13ccd-132">Konfigurieren von Internetanwendungen</span><span class="sxs-lookup"><span data-stu-id="13ccd-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="13ccd-133">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="13ccd-133">Configuration File Schema</span></span>](../index.md)
