---
title: '&lt;Entfernen Sie&gt; Bypasslist (Network Settings)-Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5c7918048743d53d8523ec399d1a11c67152a2bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742948"
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="a9764-102">&lt;Entfernen Sie&gt; Bypasslist (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="a9764-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="a9764-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxyumgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="a9764-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="a9764-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a9764-104">\<configuration></span></span>  
<span data-ttu-id="a9764-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a9764-105">\<system.net></span></span>  
<span data-ttu-id="a9764-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="a9764-106">\<defaultProxy></span></span>  
<span data-ttu-id="a9764-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="a9764-107">\<bypasslist></span></span>  
<span data-ttu-id="a9764-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="a9764-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9764-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9764-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9764-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9764-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a9764-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9764-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9764-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9764-112">Attributes</span></span>  
  
|<span data-ttu-id="a9764-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="a9764-113">**Attribute**</span></span>|<span data-ttu-id="a9764-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a9764-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="a9764-115">Ein regulärer Ausdruck, die eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a9764-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9764-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9764-116">Child Elements</span></span>  
 <span data-ttu-id="a9764-117">Keine</span><span class="sxs-lookup"><span data-stu-id="a9764-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9764-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9764-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a9764-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a9764-119">**Element**</span></span>|<span data-ttu-id="a9764-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a9764-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a9764-121">BypassList</span><span class="sxs-lookup"><span data-stu-id="a9764-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="a9764-122">Stellt einen Satz von regulären Ausdrücken, die Beschreibung der Adressen, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9764-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9764-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9764-123">Remarks</span></span>  
 <span data-ttu-id="a9764-124">Die `remove` -Element entfernt reguläre Ausdrücke, die IP-Adressen oder DNS-Servernamen aus der Liste der Adressen, die einen Proxyserver umgehen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a9764-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="a9764-125">Die Adressen wurden früher in der Konfigurationsdatei oder auf einer höheren Ebene in der Hierarchie definiert.</span><span class="sxs-lookup"><span data-stu-id="a9764-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="a9764-126">Der Wert für die `address` Attribut muss ein regulärer Ausdruck, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a9764-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="a9764-127">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a9764-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a9764-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a9764-128">Configuration Files</span></span>  
 <span data-ttu-id="a9764-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9764-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9764-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9764-130">Example</span></span>  
 <span data-ttu-id="a9764-131">Im folgende Beispiel vorherige Definition für die Domäne Adventure-works.com entfernt und anschließend die Umgehungsliste der Domäne "contoso.com" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9764-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a9764-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9764-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="a9764-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a9764-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
