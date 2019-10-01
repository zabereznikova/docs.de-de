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
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698148"
---
# <a name="network-settings-schema"></a><span data-ttu-id="c630d-102">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="c630d-102">Network Settings Schema</span></span>
<span data-ttu-id="c630d-103">Netzwerkeinstellungen geben an, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c630d-103">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="c630d-104">Die @no__t -0system. net > Einstellungen geben an, wie der .NET Framework eine Verbindung mit dem Netzwerk herstellt.</span><span class="sxs-lookup"><span data-stu-id="c630d-104">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="c630d-105">Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<system.Net>-Elements (Netzwerkeinstellungen)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c630d-105">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="c630d-106">Element</span><span class="sxs-lookup"><span data-stu-id="c630d-106">Element</span></span>|<span data-ttu-id="c630d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c630d-107">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c630d-108">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-108">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="c630d-109">Gibt die Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c630d-109">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="c630d-110">\<connectionManagement>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-110">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="c630d-111">Gibt die maximale Anzahl von Verbindungen mit Internethosts an.</span><span class="sxs-lookup"><span data-stu-id="c630d-111">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="c630d-112">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-112">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c630d-113">Gibt den Proxyserver an, der für HTTP-Anforderungen an das Internet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c630d-113">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="c630d-114">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-114">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="c630d-115">Enthält Einstellungen für E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="c630d-115">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="c630d-116">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-116">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="c630d-117">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c630d-117">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="c630d-118">\<webRequestModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-118">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="c630d-119">Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c630d-119">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="c630d-120">Die \<uri-> Einstellungen geben an, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="c630d-120">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="c630d-121">In der folgenden Tabelle wird die Funktion der einzelnen untergeordneten Konfigurationselemente unter dem [>-Element \<uri beschrieben (URI-Einstellungen)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c630d-121">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="c630d-122">Element</span><span class="sxs-lookup"><span data-stu-id="c630d-122">Element</span></span>|<span data-ttu-id="c630d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c630d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c630d-124">\<idn>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-124">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="c630d-125">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c630d-125">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="c630d-126">\<iriParsing>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-126">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="c630d-127">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c630d-127">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="c630d-128">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="c630d-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="c630d-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="c630d-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c630d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c630d-130">See also</span></span>

- [<span data-ttu-id="c630d-131">Konfigurieren von Internetanwendungen</span><span class="sxs-lookup"><span data-stu-id="c630d-131">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="c630d-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c630d-132">Configuration File Schema</span></span>](../index.md)
