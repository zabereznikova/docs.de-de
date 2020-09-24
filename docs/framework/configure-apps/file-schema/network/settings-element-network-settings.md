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
ms.openlocfilehash: c5fe0b9eccd1c429c0041fcfab06b0cc20a20aa2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167274"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="b8359-102">\<settings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8359-102">\<settings> Element (Network Settings)</span></span>

<span data-ttu-id="b8359-103">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="b8359-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="b8359-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8359-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8359-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b8359-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b8359-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8359-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8359-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b8359-107">Attributes</span></span>  

 <span data-ttu-id="b8359-108">Keine</span><span class="sxs-lookup"><span data-stu-id="b8359-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8359-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8359-109">Child Elements</span></span>  
  
|<span data-ttu-id="b8359-110">Element</span><span class="sxs-lookup"><span data-stu-id="b8359-110">Element</span></span>|<span data-ttu-id="b8359-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8359-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8359-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="b8359-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="b8359-113">Passt Parameter an, die von der-Klasse verwendet werden <xref:System.Net.HttpListener> .</span><span class="sxs-lookup"><span data-stu-id="b8359-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b8359-114">HttpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b8359-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="b8359-115">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b8359-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b8359-116">IPv6</span><span class="sxs-lookup"><span data-stu-id="b8359-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="b8359-117">Aktiviert die IPv6-Unterstützung (Internet Protocol Version 6).</span><span class="sxs-lookup"><span data-stu-id="b8359-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b8359-118">\<performanceCounter>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8359-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="b8359-119">Aktiviert Netzwerk Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="b8359-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b8359-120">ServicePointManager</span><span class="sxs-lookup"><span data-stu-id="b8359-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="b8359-121">Konfiguriert Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="b8359-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b8359-122">Glühbirne</span><span class="sxs-lookup"><span data-stu-id="b8359-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="b8359-123">Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8359-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b8359-124">\<webProxyScript>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8359-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="b8359-125">Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8359-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8359-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8359-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b8359-127">Element</span><span class="sxs-lookup"><span data-stu-id="b8359-127">Element</span></span>|<span data-ttu-id="b8359-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8359-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8359-129">system.net</span><span class="sxs-lookup"><span data-stu-id="b8359-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b8359-130">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b8359-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8359-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b8359-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b8359-132">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b8359-132">Configuration Files</span></span>  

 <span data-ttu-id="b8359-133">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8359-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8359-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8359-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="b8359-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8359-135">Network Settings Schema</span></span>](index.md)
