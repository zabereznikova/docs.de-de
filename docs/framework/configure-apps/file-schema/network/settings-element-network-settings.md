---
title: '&lt;Einstellungen&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9d6189c736e1f2843a986c3a96f8547e9a231db0
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862684"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="72909-102">&lt;Einstellungen&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="72909-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="72909-103">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="72909-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="72909-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="72909-104">\<configuration></span></span>  
<span data-ttu-id="72909-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="72909-105">\<system.net></span></span>  
<span data-ttu-id="72909-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="72909-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72909-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="72909-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72909-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72909-108">Attributes and Elements</span></span>  
 <span data-ttu-id="72909-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72909-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72909-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="72909-110">Attributes</span></span>  
 <span data-ttu-id="72909-111">Keine</span><span class="sxs-lookup"><span data-stu-id="72909-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="72909-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72909-112">Child Elements</span></span>  
  
|<span data-ttu-id="72909-113">Element</span><span class="sxs-lookup"><span data-stu-id="72909-113">Element</span></span>|<span data-ttu-id="72909-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72909-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72909-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="72909-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="72909-116">Passt die Parameter ein, die die <xref:System.Net.HttpListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="72909-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="72909-117">"HttpWebRequest"</span><span class="sxs-lookup"><span data-stu-id="72909-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="72909-118">Passt die Web-Anforderungsparameter.</span><span class="sxs-lookup"><span data-stu-id="72909-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="72909-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="72909-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="72909-120">Ermöglicht es Internet Protocol, Version 6 (IPv6) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="72909-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="72909-121">\<PerformanceCounter >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="72909-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="72909-122">Ermöglicht das Netzwerk-Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="72909-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="72909-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="72909-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="72909-124">Konfiguriert die Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="72909-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="72909-125">Socket</span><span class="sxs-lookup"><span data-stu-id="72909-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="72909-126">Gibt an, ob es sich bei Socketvorgänge Abschlussports verwenden.</span><span class="sxs-lookup"><span data-stu-id="72909-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="72909-127">\<WebProxyScript >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="72909-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="72909-128">Konfiguriert die Eigenschaften des Skripts zur Ermittlung von Webproxys, verwendet.</span><span class="sxs-lookup"><span data-stu-id="72909-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72909-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72909-129">Parent Elements</span></span>  
  
|<span data-ttu-id="72909-130">Element</span><span class="sxs-lookup"><span data-stu-id="72909-130">Element</span></span>|<span data-ttu-id="72909-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72909-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72909-132">System.NET</span><span class="sxs-lookup"><span data-stu-id="72909-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="72909-133">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="72909-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72909-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72909-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="72909-135">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="72909-135">Configuration Files</span></span>  
 <span data-ttu-id="72909-136">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72909-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72909-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72909-137">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 [<span data-ttu-id="72909-138">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="72909-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
