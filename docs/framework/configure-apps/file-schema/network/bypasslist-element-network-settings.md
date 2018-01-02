---
title: '&lt;BypassList&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 20e3676e69357dc73433876275cb2737ee235552
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="6525b-102">&lt;BypassList&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6525b-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="6525b-103">Stellt einen Satz von regulären Ausdrücken, die Beschreibung der Adressen, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="6525b-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="6525b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6525b-104">\<configuration></span></span>  
<span data-ttu-id="6525b-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="6525b-105">\<system.net></span></span>  
<span data-ttu-id="6525b-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="6525b-106">\<defaultProxy></span></span>  
<span data-ttu-id="6525b-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="6525b-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6525b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6525b-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6525b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6525b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6525b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6525b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6525b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6525b-111">Attributes</span></span>  
 <span data-ttu-id="6525b-112">Keine</span><span class="sxs-lookup"><span data-stu-id="6525b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6525b-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6525b-113">Child Elements</span></span>  
  
|<span data-ttu-id="6525b-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="6525b-114">**Element**</span></span>|<span data-ttu-id="6525b-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6525b-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6525b-116">add</span><span class="sxs-lookup"><span data-stu-id="6525b-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="6525b-117">Fügt eine IP-Adresse oder einen DNS-Namen, die Proxyumgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="6525b-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="6525b-118">clear</span><span class="sxs-lookup"><span data-stu-id="6525b-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="6525b-119">Löscht die Bypass-Liste.</span><span class="sxs-lookup"><span data-stu-id="6525b-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="6525b-120">remove</span><span class="sxs-lookup"><span data-stu-id="6525b-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="6525b-121">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxyumgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="6525b-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6525b-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6525b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6525b-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="6525b-123">**Element**</span></span>|<span data-ttu-id="6525b-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6525b-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6525b-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="6525b-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="6525b-126">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="6525b-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6525b-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6525b-127">Remarks</span></span>  
 <span data-ttu-id="6525b-128">Die Umgehungsliste enthält reguläre Ausdrücke, die URIs zu beschreiben, <xref:System.Net.WebRequest> Instanzen direkt anstelle von zuzugreifen, über den Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="6525b-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="6525b-129">Sie sollten Vorsicht walten, wenn Sie für dieses Element einen regulären Ausdruck angeben.</span><span class="sxs-lookup"><span data-stu-id="6525b-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="6525b-130">Der reguläre Ausdruck "[a-Z] +\\.contoso\\.com" entspricht, die jedem host in der Domäne "contoso.com", sondern auch mit jedem Host in der Domäne contoso.com.cpandl.com überein.</span><span class="sxs-lookup"><span data-stu-id="6525b-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="6525b-131">Um nur einen Host in der Domäne "contoso.com" zu vergleichen, verwenden Sie einen Anker ("$"): "[a-Z] +\\.contoso\\".com "$".</span><span class="sxs-lookup"><span data-stu-id="6525b-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="6525b-132">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6525b-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6525b-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="6525b-133">Configuration Files</span></span>  
 <span data-ttu-id="6525b-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6525b-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6525b-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6525b-135">Example</span></span>  
 <span data-ttu-id="6525b-136">Im folgende Beispiel wird die Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6525b-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="6525b-137">Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite umgeht den Proxy für alle Server, deren IP-Adressen beginnen mit 192.168.</span><span class="sxs-lookup"><span data-stu-id="6525b-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6525b-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6525b-138">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="6525b-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6525b-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
