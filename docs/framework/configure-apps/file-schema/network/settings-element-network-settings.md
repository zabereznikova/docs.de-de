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
ms.openlocfilehash: 12797e2f06d03aacd81700eae57d5776c1a6f354
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663996"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="1fb0f-102">\<Settings >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1fb0f-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="1fb0f-103">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="1fb0f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1fb0f-104">\<configuration></span></span>  
<span data-ttu-id="1fb0f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1fb0f-105">\<system.net></span></span>  
<span data-ttu-id="1fb0f-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="1fb0f-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb0f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fb0f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fb0f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1fb0f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1fb0f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fb0f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1fb0f-110">Attributes</span></span>  
 <span data-ttu-id="1fb0f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="1fb0f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1fb0f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1fb0f-112">Child Elements</span></span>  
  
|<span data-ttu-id="1fb0f-113">Element</span><span class="sxs-lookup"><span data-stu-id="1fb0f-113">Element</span></span>|<span data-ttu-id="1fb0f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fb0f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fb0f-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="1fb0f-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="1fb0f-116">Passt Parameter an, die von <xref:System.Net.HttpListener> der-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="1fb0f-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="1fb0f-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="1fb0f-118">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="1fb0f-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="1fb0f-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="1fb0f-120">Aktiviert die IPv6-Unterstützung (Internet Protocol Version 6).</span><span class="sxs-lookup"><span data-stu-id="1fb0f-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="1fb0f-121">\<Performance Counter >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1fb0f-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="1fb0f-122">Aktiviert Netzwerk Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="1fb0f-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="1fb0f-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="1fb0f-124">Konfiguriert Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="1fb0f-125">Glühbirne</span><span class="sxs-lookup"><span data-stu-id="1fb0f-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="1fb0f-126">Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="1fb0f-127">\<WebProxyScript >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1fb0f-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="1fb0f-128">Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fb0f-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1fb0f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1fb0f-130">Element</span><span class="sxs-lookup"><span data-stu-id="1fb0f-130">Element</span></span>|<span data-ttu-id="1fb0f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fb0f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fb0f-132">system.net</span><span class="sxs-lookup"><span data-stu-id="1fb0f-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1fb0f-133">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fb0f-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1fb0f-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1fb0f-135">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="1fb0f-135">Configuration Files</span></span>  
 <span data-ttu-id="1fb0f-136">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fb0f-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb0f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fb0f-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="1fb0f-138">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1fb0f-138">Network Settings Schema</span></span>](index.md)
