---
title: <ipv6>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088137"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="9750a-102">\<ipv6>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9750a-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="9750a-103">Aktiviert IPv6-Antworten (Internet Protokollversion 6) von veralteten Membern der- <xref:System.Net.Dns> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9750a-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="9750a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9750a-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9750a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9750a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9750a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9750a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9750a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="9750a-107">Attributes</span></span>  
  
|<span data-ttu-id="9750a-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="9750a-108">**Attribute**</span></span>|<span data-ttu-id="9750a-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9750a-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="9750a-110">Gibt an, ob Member der- <xref:System.Net.Dns> Klasse IPv6 (Internet Protocol Version 6)-Adressen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9750a-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="9750a-111">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9750a-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9750a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9750a-112">Child Elements</span></span>  
 <span data-ttu-id="9750a-113">Keine</span><span class="sxs-lookup"><span data-stu-id="9750a-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9750a-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9750a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9750a-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="9750a-115">**Element**</span></span>|<span data-ttu-id="9750a-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9750a-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9750a-117">settings</span><span class="sxs-lookup"><span data-stu-id="9750a-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="9750a-118">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="9750a-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9750a-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9750a-119">Remarks</span></span>  
 <span data-ttu-id="9750a-120">Diese Einstellung aktiviert die IPv6-Unterstützung für die veralteten Member der <xref:System.Net.Dns> -Klasse: <xref:System.Net.Dns.BeginGetHostByName%2A> , <xref:System.Net.Dns.BeginResolve%2A> , <xref:System.Net.Dns.EndGetHostByName%2A> , <xref:System.Net.Dns.EndResolve%2A> , <xref:System.Net.Dns.GetHostByAddress%2A> , <xref:System.Net.Dns.GetHostByName%2A> und <xref:System.Net.Dns.Resolve%2A> .</span><span class="sxs-lookup"><span data-stu-id="9750a-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="9750a-121">Bei anderen Membern des- <xref:System.Net?displayProperty=nameWithType> Namespace werden möglicherweise IPv6-Adressen zurückgegeben, wenn IPv6 im Betriebssystem aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9750a-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9750a-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="9750a-122">Configuration Files</span></span>  
 <span data-ttu-id="9750a-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9750a-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9750a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9750a-124">Example</span></span>  
 <span data-ttu-id="9750a-125">Im folgenden Beispiel wird gezeigt, wie die IPv6-Unterstützung für die-Klasse aktiviert wird <xref:System.Net.Dns> .</span><span class="sxs-lookup"><span data-stu-id="9750a-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9750a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9750a-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9750a-127">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="9750a-127">Network Settings Schema</span></span>](index.md)
