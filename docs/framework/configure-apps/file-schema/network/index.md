---
title: Netzwerkeinstellungsschema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ca4a0000d85c8fbac9a723beeda51f9c7886ed8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="network-settings-schema"></a><span data-ttu-id="8a6f8-102">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="8a6f8-102">Network Settings Schema</span></span>
<span data-ttu-id="8a6f8-103">Netzwerkeinstellungen geben an, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="8a6f8-104">Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<system.Net>-Elements (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8a6f8-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="8a6f8-105">Element</span><span class="sxs-lookup"><span data-stu-id="8a6f8-105">Element</span></span>|<span data-ttu-id="8a6f8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a6f8-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a6f8-107">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="8a6f8-108">Gibt die Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="8a6f8-109">\<connectionManagement>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="8a6f8-110">Gibt die maximale Anzahl von Verbindungen mit Internethosts an.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="8a6f8-111">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="8a6f8-112">Gibt den Proxyserver an, der für HTTP-Anforderungen an das Internet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="8a6f8-113">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="8a6f8-114">Enthält Einstellungen für E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="8a6f8-115">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="8a6f8-116">Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-116">Specifies the modules used to request information from Internet hosts.</span></span>|  
|[<span data-ttu-id="8a6f8-117">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-117">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="8a6f8-118">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-118">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>|  
|[<span data-ttu-id="8a6f8-119">\<webRequestModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-119">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="8a6f8-120">Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="8a6f8-121">URI-Einstellungen geben an, wie .NET Framework Webadressen behandelt, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-121">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="8a6f8-122">Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<Uri>-Elements (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8a6f8-122">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="8a6f8-123">Element</span><span class="sxs-lookup"><span data-stu-id="8a6f8-123">Element</span></span>|<span data-ttu-id="8a6f8-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a6f8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a6f8-125">\<idn>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-125">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="8a6f8-126">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="8a6f8-127">\<iriParsing>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-127">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="8a6f8-128">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="8a6f8-129">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a6f8-129">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="8a6f8-130">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f8-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a6f8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a6f8-131">See Also</span></span>  
 [<span data-ttu-id="8a6f8-132">Konfigurieren von Internetanwendungen</span><span class="sxs-lookup"><span data-stu-id="8a6f8-132">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="8a6f8-133">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="8a6f8-133">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
