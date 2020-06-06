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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154945"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="a9f51-102">\<bypasslist>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a9f51-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="a9f51-103">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9f51-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="a9f51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9f51-104">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9f51-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9f51-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a9f51-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9f51-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9f51-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9f51-107">Attributes</span></span>  
 <span data-ttu-id="a9f51-108">Keine</span><span class="sxs-lookup"><span data-stu-id="a9f51-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9f51-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9f51-109">Child Elements</span></span>  
  
|<span data-ttu-id="a9f51-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="a9f51-110">**Element**</span></span>|<span data-ttu-id="a9f51-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a9f51-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a9f51-112">add</span><span class="sxs-lookup"><span data-stu-id="a9f51-112">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a9f51-113">Fügt der Proxy Umgehungs Liste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9f51-113">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="a9f51-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="a9f51-114">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a9f51-115">Löscht die Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="a9f51-115">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="a9f51-116">remove</span><span class="sxs-lookup"><span data-stu-id="a9f51-116">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a9f51-117">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="a9f51-117">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9f51-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9f51-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a9f51-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a9f51-119">**Element**</span></span>|<span data-ttu-id="a9f51-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a9f51-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a9f51-121">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="a9f51-121">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="a9f51-122">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a9f51-122">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9f51-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a9f51-123">Remarks</span></span>  
 <span data-ttu-id="a9f51-124">Die Umgehungs Liste enthält reguläre Ausdrücke, die URIs beschreiben, <xref:System.Net.WebRequest> auf die Instanzen direkt anstatt über den Proxy Server zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a9f51-124">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="a9f51-125">Sie sollten Vorsicht walten lassen, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="a9f51-125">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="a9f51-126">Der reguläre Ausdruck "[a-z] + \\ ..................................... \\</span><span class="sxs-lookup"><span data-stu-id="a9f51-126">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="a9f51-127">Um nur einen Host in der contoso.com-Domäne zu finden, verwenden Sie einen Anker ("$"): "[a-z] + \\ .. \\ .</span><span class="sxs-lookup"><span data-stu-id="a9f51-127">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="a9f51-128">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [.NET Framework reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a9f51-128">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a9f51-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a9f51-129">Configuration Files</span></span>  
 <span data-ttu-id="a9f51-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9f51-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f51-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9f51-131">Example</span></span>  
 <span data-ttu-id="a9f51-132">Im folgenden Beispiel werden der Umgehungs Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9f51-132">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="a9f51-133">Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adressen mit 192,168 beginnen.</span><span class="sxs-lookup"><span data-stu-id="a9f51-133">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a9f51-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9f51-134">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a9f51-135">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="a9f51-135">Network Settings Schema</span></span>](index.md)
