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
ms.openlocfilehash: b8969cecf8ffb2ef23522f193bb322b1170e6111
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089210"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="affd9-102">\<IPv6>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="affd9-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="affd9-103">Internetprotokoll Version 6 (IPv6) ermöglicht Antworten von veralteten Member, der die <xref:System.Net.Dns> Klasse.</span><span class="sxs-lookup"><span data-stu-id="affd9-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="affd9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="affd9-104">\<configuration></span></span>  
<span data-ttu-id="affd9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="affd9-105">\<system.net></span></span>  
<span data-ttu-id="affd9-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="affd9-106">\<settings></span></span>  
<span data-ttu-id="affd9-107">\<ipv6></span><span class="sxs-lookup"><span data-stu-id="affd9-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="affd9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="affd9-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="affd9-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="affd9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="affd9-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="affd9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="affd9-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="affd9-111">Attributes</span></span>  
  
|<span data-ttu-id="affd9-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="affd9-112">**Attribute**</span></span>|<span data-ttu-id="affd9-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="affd9-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="affd9-114">Gibt an, ob Mitglieder der <xref:System.Net.Dns> Klasse zurückgeben Internet Protocol, Version 6 (IPv6)-Adressen.</span><span class="sxs-lookup"><span data-stu-id="affd9-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="affd9-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="affd9-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="affd9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="affd9-116">Child Elements</span></span>  
 <span data-ttu-id="affd9-117">Keine</span><span class="sxs-lookup"><span data-stu-id="affd9-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="affd9-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="affd9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="affd9-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="affd9-119">**Element**</span></span>|<span data-ttu-id="affd9-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="affd9-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="affd9-121">settings</span><span class="sxs-lookup"><span data-stu-id="affd9-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="affd9-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="affd9-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="affd9-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="affd9-123">Remarks</span></span>  
 <span data-ttu-id="affd9-124">Diese Einstellung ermöglicht IPv6-Unterstützung für die veralteten Member von der <xref:System.Net.Dns> Klasse: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, und <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="affd9-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="affd9-125">Für andere Teammitglieder die <xref:System.Net?displayProperty=nameWithType> -Namespace, IPv6-Adressen können zurückgegeben werden, wenn IPv6 im Betriebssystem aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="affd9-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="affd9-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="affd9-126">Configuration Files</span></span>  
 <span data-ttu-id="affd9-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="affd9-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="affd9-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd9-128">Example</span></span>  
 <span data-ttu-id="affd9-129">Das folgende Beispiel zeigt, wie Sie IPv6-Unterstützung für aktivieren die <xref:System.Net.Dns> Klasse.</span><span class="sxs-lookup"><span data-stu-id="affd9-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="affd9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="affd9-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="affd9-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="affd9-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
