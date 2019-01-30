---
title: <settings>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 839907d9339d459070fff12dbca22d3c2df5b020
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260618"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="a2e10-102">\<Einstellungen >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2e10-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="a2e10-103">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a2e10-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="a2e10-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2e10-104">\<configuration></span></span>  
<span data-ttu-id="a2e10-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a2e10-105">\<system.net></span></span>  
<span data-ttu-id="a2e10-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="a2e10-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e10-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2e10-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2e10-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2e10-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2e10-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2e10-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2e10-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2e10-110">Attributes</span></span>  
 <span data-ttu-id="a2e10-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a2e10-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2e10-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2e10-112">Child Elements</span></span>  
  
|<span data-ttu-id="a2e10-113">Element</span><span class="sxs-lookup"><span data-stu-id="a2e10-113">Element</span></span>|<span data-ttu-id="a2e10-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2e10-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2e10-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="a2e10-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="a2e10-116">Passt die Parameter ein, die die <xref:System.Net.HttpListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a2e10-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="a2e10-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="a2e10-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="a2e10-118">Passt die Web-Anforderungsparameter.</span><span class="sxs-lookup"><span data-stu-id="a2e10-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="a2e10-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="a2e10-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="a2e10-120">Ermöglicht es Internet Protocol, Version 6 (IPv6) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a2e10-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="a2e10-121">\<PerformanceCounter >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2e10-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="a2e10-122">Ermöglicht das Netzwerk-Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="a2e10-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="a2e10-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="a2e10-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="a2e10-124">Konfiguriert die Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="a2e10-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="a2e10-125">socket</span><span class="sxs-lookup"><span data-stu-id="a2e10-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="a2e10-126">Gibt an, ob es sich bei Socketvorgänge Abschlussports verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2e10-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="a2e10-127">\<WebProxyScript >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2e10-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="a2e10-128">Konfiguriert die Eigenschaften des Skripts zur Ermittlung von Webproxys, verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2e10-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2e10-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2e10-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a2e10-130">Element</span><span class="sxs-lookup"><span data-stu-id="a2e10-130">Element</span></span>|<span data-ttu-id="a2e10-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2e10-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2e10-132">system.net</span><span class="sxs-lookup"><span data-stu-id="a2e10-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="a2e10-133">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a2e10-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2e10-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2e10-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a2e10-135">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a2e10-135">Configuration Files</span></span>  
 <span data-ttu-id="a2e10-136">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2e10-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e10-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2e10-137">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="a2e10-138">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2e10-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
