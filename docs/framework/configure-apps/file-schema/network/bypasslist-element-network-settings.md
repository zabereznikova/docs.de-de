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
ms.openlocfilehash: 7a6c1282c9ca8381d2dbb21ffdc82f95732c42b3
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087521"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="c7abd-102">\<BypassList >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c7abd-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="c7abd-103">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7abd-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="c7abd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7abd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7abd-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c7abd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c7abd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c7abd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="c7abd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<BypassList >**</span><span class="sxs-lookup"><span data-stu-id="c7abd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c7abd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7abd-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7abd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c7abd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c7abd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7abd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7abd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c7abd-111">Attributes</span></span>  
 <span data-ttu-id="c7abd-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c7abd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c7abd-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7abd-113">Child Elements</span></span>  
  
|<span data-ttu-id="c7abd-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="c7abd-114">**Element**</span></span>|<span data-ttu-id="c7abd-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c7abd-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c7abd-116">add</span><span class="sxs-lookup"><span data-stu-id="c7abd-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c7abd-117">Fügt der Proxy Umgehungs Liste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7abd-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="c7abd-118">clear</span><span class="sxs-lookup"><span data-stu-id="c7abd-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c7abd-119">Löscht die Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="c7abd-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="c7abd-120">remove</span><span class="sxs-lookup"><span data-stu-id="c7abd-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c7abd-121">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="c7abd-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7abd-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7abd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c7abd-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="c7abd-123">**Element**</span></span>|<span data-ttu-id="c7abd-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c7abd-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c7abd-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c7abd-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c7abd-126">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="c7abd-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7abd-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7abd-127">Remarks</span></span>  
 <span data-ttu-id="c7abd-128">Die Umgehungs Liste enthält reguläre Ausdrücke, mit denen URIs beschrieben werden, die <xref:System.Net.WebRequest> Instanzen direkt anstatt über den Proxy Server auf die Instanzen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7abd-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="c7abd-129">Sie sollten Vorsicht walten lassen, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="c7abd-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="c7abd-130">Der reguläre Ausdruck "[a-z] +\\.\\. com" stimmt mit jedem Host in der contoso.com-Domäne überein, aber auch mit jedem Host in der contoso.com.cpandl.com-Domäne überein.</span><span class="sxs-lookup"><span data-stu-id="c7abd-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="c7abd-131">Um nur einen Host in der contoso.com-Domäne zu finden, verwenden Sie einen Anker ("$"): "[a-z] +\\.\\. com $".</span><span class="sxs-lookup"><span data-stu-id="c7abd-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="c7abd-132">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [.NET Framework reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c7abd-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c7abd-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c7abd-133">Configuration Files</span></span>  
 <span data-ttu-id="c7abd-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7abd-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7abd-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7abd-135">Example</span></span>  
 <span data-ttu-id="c7abd-136">Im folgenden Beispiel werden der Umgehungs Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7abd-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="c7abd-137">Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adressen mit 192,168 beginnen.</span><span class="sxs-lookup"><span data-stu-id="c7abd-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7abd-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7abd-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c7abd-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c7abd-139">Network Settings Schema</span></span>](index.md)
