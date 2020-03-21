---
title: <bypasslist>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154945"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="52788-102">\<Bypasslist> Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="52788-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="52788-103">Stellt eine Reihe regulärer Ausdrücke bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="52788-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="52788-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52788-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52788-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="52788-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="52788-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="52788-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="52788-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Bypasslist>**</span><span class="sxs-lookup"><span data-stu-id="52788-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="52788-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="52788-108">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52788-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="52788-109">Attributes and Elements</span></span>  
 <span data-ttu-id="52788-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52788-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52788-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="52788-111">Attributes</span></span>  
 <span data-ttu-id="52788-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="52788-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52788-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="52788-113">Child Elements</span></span>  
  
|<span data-ttu-id="52788-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="52788-114">**Element**</span></span>|<span data-ttu-id="52788-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="52788-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="52788-116">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="52788-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="52788-117">Fügt der Proxyumgehungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="52788-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="52788-118">Klar</span><span class="sxs-lookup"><span data-stu-id="52788-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="52788-119">Löscht die Umgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="52788-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="52788-120">Entfernen</span><span class="sxs-lookup"><span data-stu-id="52788-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="52788-121">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxyumgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="52788-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52788-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="52788-122">Parent Elements</span></span>  
  
|<span data-ttu-id="52788-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="52788-123">**Element**</span></span>|<span data-ttu-id="52788-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="52788-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="52788-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="52788-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="52788-126">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="52788-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52788-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="52788-127">Remarks</span></span>  
 <span data-ttu-id="52788-128">Die Umgehungsliste enthält reguläre Ausdrücke, die URIs beschreiben, auf die <xref:System.Net.WebRequest> Instanzen direkt statt über den Proxyserver zugreifen.</span><span class="sxs-lookup"><span data-stu-id="52788-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="52788-129">Sie sollten vorsichtshalber sein, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="52788-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="52788-130">Der reguläre Ausdruck "[a-z]+\\\\.contoso .com" entspricht jedem Host in der contoso.com Domäne, aber auch jedem Host in der contoso.com.cpandl.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="52788-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="52788-131">Um nur einen Host in der domäne contoso.com abzugleichen, verwenden Sie einen\\Anker ("-"): "[a-z]+ .contoso\\.com".</span><span class="sxs-lookup"><span data-stu-id="52788-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="52788-132">Weitere Informationen zu regulären Ausdrücken finden Sie unter . [.NET Framework Reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="52788-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="52788-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="52788-133">Configuration Files</span></span>  
 <span data-ttu-id="52788-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52788-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52788-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52788-135">Example</span></span>  
 <span data-ttu-id="52788-136">Im folgenden Beispiel werden der Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52788-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="52788-137">Die erste umgeht den Proxy für alle Server in der contoso.com Domäne. Der zweite umgeht den Proxy für alle Server, deren IP-Adressen mit 192.168 beginnen.</span><span class="sxs-lookup"><span data-stu-id="52788-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52788-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52788-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="52788-139">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="52788-139">Network Settings Schema</span></span>](index.md)
