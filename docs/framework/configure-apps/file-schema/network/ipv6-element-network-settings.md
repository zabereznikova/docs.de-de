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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088137"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="4d0b8-102">\<IPv6>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4d0b8-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="4d0b8-103">Aktiviert IPv6-Antworten (Internet Protocol Version 6) von veralteten Membern der <xref:System.Net.Dns>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

<span data-ttu-id="4d0b8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d0b8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4d0b8-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4d0b8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4d0b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Einstellungen**](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="4d0b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="4d0b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**IPv6 >**</span><span class="sxs-lookup"><span data-stu-id="4d0b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4d0b8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d0b8-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d0b8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4d0b8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d0b8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d0b8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4d0b8-111">Attributes</span></span>  
  
|<span data-ttu-id="4d0b8-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="4d0b8-112">**Attribute**</span></span>|<span data-ttu-id="4d0b8-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4d0b8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="4d0b8-114">Gibt an, ob Member der <xref:System.Net.Dns> Klasse Internet Protokollversion 6 (IPv6)-Adressen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="4d0b8-115">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d0b8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d0b8-116">Child Elements</span></span>  
 <span data-ttu-id="4d0b8-117">Keine</span><span class="sxs-lookup"><span data-stu-id="4d0b8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d0b8-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d0b8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4d0b8-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="4d0b8-119">**Element**</span></span>|<span data-ttu-id="4d0b8-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4d0b8-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4d0b8-121">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4d0b8-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4d0b8-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d0b8-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d0b8-123">Remarks</span></span>  
 <span data-ttu-id="4d0b8-124">Diese Einstellung aktiviert die IPv6-Unterstützung für veraltete Member der <xref:System.Net.Dns>-Klasse: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>und <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="4d0b8-125">Bei anderen Membern des <xref:System.Net?displayProperty=nameWithType>-Namespace werden möglicherweise IPv6-Adressen zurückgegeben, wenn IPv6 im Betriebssystem aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4d0b8-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="4d0b8-126">Configuration Files</span></span>  
 <span data-ttu-id="4d0b8-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d0b8-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d0b8-128">Example</span></span>  
 <span data-ttu-id="4d0b8-129">Im folgenden Beispiel wird gezeigt, wie die IPv6-Unterstützung für die <xref:System.Net.Dns>-Klasse aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4d0b8-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d0b8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d0b8-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4d0b8-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4d0b8-131">Network Settings Schema</span></span>](index.md)
