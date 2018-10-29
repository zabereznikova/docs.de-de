---
title: '&lt;IPv6&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 5e1afdd372c2198c00bf8c02939d2167261b5d5c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205138"
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="3591b-102">&lt;IPv6&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3591b-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3591b-103">Internetprotokoll Version 6 (IPv6) ermöglicht Antworten von veralteten Member, der die <xref:System.Net.Dns> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3591b-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="3591b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3591b-104">\<configuration></span></span>  
<span data-ttu-id="3591b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3591b-105">\<system.net></span></span>  
<span data-ttu-id="3591b-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="3591b-106">\<settings></span></span>  
<span data-ttu-id="3591b-107">\<IPv6 ></span><span class="sxs-lookup"><span data-stu-id="3591b-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3591b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3591b-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3591b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3591b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3591b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3591b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3591b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3591b-111">Attributes</span></span>  
  
|<span data-ttu-id="3591b-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="3591b-112">**Attribute**</span></span>|<span data-ttu-id="3591b-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3591b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="3591b-114">Gibt an, ob Mitglieder der <xref:System.Net.Dns> Klasse zurückgeben Internet Protocol, Version 6 (IPv6)-Adressen.</span><span class="sxs-lookup"><span data-stu-id="3591b-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="3591b-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="3591b-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3591b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3591b-116">Child Elements</span></span>  
 <span data-ttu-id="3591b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="3591b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3591b-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3591b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3591b-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="3591b-119">**Element**</span></span>|<span data-ttu-id="3591b-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3591b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3591b-121">settings</span><span class="sxs-lookup"><span data-stu-id="3591b-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="3591b-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="3591b-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3591b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3591b-123">Remarks</span></span>  
 <span data-ttu-id="3591b-124">Diese Einstellung ermöglicht IPv6-Unterstützung für die veralteten Member von der <xref:System.Net.Dns> Klasse: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, und <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="3591b-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="3591b-125">Für andere Teammitglieder die <xref:System.Net?displayProperty=nameWithType> -Namespace, IPv6-Adressen können zurückgegeben werden, wenn IPv6 im Betriebssystem aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3591b-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3591b-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="3591b-126">Configuration Files</span></span>  
 <span data-ttu-id="3591b-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3591b-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3591b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3591b-128">Example</span></span>  
 <span data-ttu-id="3591b-129">Das folgende Beispiel zeigt, wie Sie IPv6-Unterstützung für aktivieren die <xref:System.Net.Dns> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3591b-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3591b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3591b-130">See Also</span></span>  
- <xref:System.Net?displayProperty=nameWithType>  
- <xref:System.Net.Dns?displayProperty=nameWithType>  
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="3591b-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3591b-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
