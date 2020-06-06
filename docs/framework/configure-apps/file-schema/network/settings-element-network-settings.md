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
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089118"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="3faea-102">\<settings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3faea-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="3faea-103">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="3faea-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="3faea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3faea-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3faea-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3faea-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3faea-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3faea-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3faea-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3faea-107">Attributes</span></span>  
 <span data-ttu-id="3faea-108">Keine</span><span class="sxs-lookup"><span data-stu-id="3faea-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3faea-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3faea-109">Child Elements</span></span>  
  
|<span data-ttu-id="3faea-110">Element</span><span class="sxs-lookup"><span data-stu-id="3faea-110">Element</span></span>|<span data-ttu-id="3faea-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3faea-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3faea-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="3faea-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="3faea-113">Passt Parameter an, die von der-Klasse verwendet werden <xref:System.Net.HttpListener> .</span><span class="sxs-lookup"><span data-stu-id="3faea-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="3faea-114">HttpWebRequest</span><span class="sxs-lookup"><span data-stu-id="3faea-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="3faea-115">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="3faea-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="3faea-116">IPv6</span><span class="sxs-lookup"><span data-stu-id="3faea-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="3faea-117">Aktiviert die IPv6-Unterstützung (Internet Protocol Version 6).</span><span class="sxs-lookup"><span data-stu-id="3faea-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="3faea-118">\<performanceCounter>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3faea-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="3faea-119">Aktiviert Netzwerk Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="3faea-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="3faea-120">ServicePointManager</span><span class="sxs-lookup"><span data-stu-id="3faea-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="3faea-121">Konfiguriert Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="3faea-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="3faea-122">Glühbirne</span><span class="sxs-lookup"><span data-stu-id="3faea-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="3faea-123">Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="3faea-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="3faea-124">\<webProxyScript>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3faea-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="3faea-125">Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3faea-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3faea-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3faea-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3faea-127">Element</span><span class="sxs-lookup"><span data-stu-id="3faea-127">Element</span></span>|<span data-ttu-id="3faea-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3faea-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3faea-129">system.net</span><span class="sxs-lookup"><span data-stu-id="3faea-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="3faea-130">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3faea-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3faea-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3faea-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3faea-132">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="3faea-132">Configuration Files</span></span>  
 <span data-ttu-id="3faea-133">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3faea-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3faea-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3faea-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="3faea-135">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="3faea-135">Network Settings Schema</span></span>](index.md)
