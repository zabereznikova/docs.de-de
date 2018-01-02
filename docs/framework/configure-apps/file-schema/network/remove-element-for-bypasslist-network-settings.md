---
title: '&lt;Entfernen Sie&gt; Bypasslist (Network Settings)-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: a385401217c10a316268f48757e46e3d0cfea09c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="a8207-102">&lt;Entfernen Sie&gt; Bypasslist (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="a8207-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="a8207-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxyumgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="a8207-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="a8207-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a8207-104">\<configuration></span></span>  
<span data-ttu-id="a8207-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="a8207-105">\<system.net></span></span>  
<span data-ttu-id="a8207-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="a8207-106">\<defaultProxy></span></span>  
<span data-ttu-id="a8207-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="a8207-107">\<bypasslist></span></span>  
<span data-ttu-id="a8207-108">\<Entfernen ></span><span class="sxs-lookup"><span data-stu-id="a8207-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8207-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8207-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8207-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a8207-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a8207-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a8207-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8207-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a8207-112">Attributes</span></span>  
  
|<span data-ttu-id="a8207-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="a8207-113">**Attribute**</span></span>|<span data-ttu-id="a8207-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a8207-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="a8207-115">Ein regulärer Ausdruck, die eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a8207-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8207-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a8207-116">Child Elements</span></span>  
 <span data-ttu-id="a8207-117">Keine</span><span class="sxs-lookup"><span data-stu-id="a8207-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8207-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a8207-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a8207-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a8207-119">**Element**</span></span>|<span data-ttu-id="a8207-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a8207-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a8207-121">BypassList</span><span class="sxs-lookup"><span data-stu-id="a8207-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="a8207-122">Stellt einen Satz von regulären Ausdrücken, die Beschreibung der Adressen, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8207-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8207-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8207-123">Remarks</span></span>  
 <span data-ttu-id="a8207-124">Die `remove` -Element entfernt reguläre Ausdrücke, die IP-Adressen oder DNS-Servernamen aus der Liste der Adressen, die einen Proxyserver umgehen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a8207-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="a8207-125">Die Adressen wurden früher in der Konfigurationsdatei oder auf einer höheren Ebene in der Hierarchie definiert.</span><span class="sxs-lookup"><span data-stu-id="a8207-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="a8207-126">Der Wert für die `address` Attribut muss ein regulärer Ausdruck, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a8207-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="a8207-127">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a8207-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a8207-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a8207-128">Configuration Files</span></span>  
 <span data-ttu-id="a8207-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8207-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8207-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8207-130">Example</span></span>  
 <span data-ttu-id="a8207-131">Im folgende Beispiel vorherige Definition für die Domäne Adventure-works.com entfernt und anschließend die Umgehungsliste der Domäne "contoso.com" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8207-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8207-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8207-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="a8207-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a8207-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
