---
title: <add>-Element für bypasslist (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155076"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="69533-102">\<Hinzufügen> Elements für Bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="69533-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="69533-103">Fügt der Proxyumgehungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="69533-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="69533-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="69533-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="69533-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="69533-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="69533-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="69533-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="69533-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bypasslist>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="69533-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="69533-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="69533-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69533-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="69533-109">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69533-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69533-110">Attributes and Elements</span></span>  
 <span data-ttu-id="69533-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69533-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69533-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="69533-112">Attributes</span></span>  
  
|<span data-ttu-id="69533-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="69533-113">**Attribute**</span></span>|<span data-ttu-id="69533-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69533-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="69533-115">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="69533-115">**address**</span></span>|<span data-ttu-id="69533-116">Ein regulärer Ausdruck, der eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="69533-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69533-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69533-117">Child Elements</span></span>  
 <span data-ttu-id="69533-118">Keine.</span><span class="sxs-lookup"><span data-stu-id="69533-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69533-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69533-119">Parent Elements</span></span>  
  
|<span data-ttu-id="69533-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="69533-120">**Element**</span></span>|<span data-ttu-id="69533-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69533-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="69533-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="69533-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="69533-123">Stellt eine Reihe regulärer Ausdrücke bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="69533-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69533-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="69533-124">Remarks</span></span>  
 <span data-ttu-id="69533-125">Das `add` Element fügt reguläre Ausdrücke ein, die IP-Adressen oder DNS-Servernamen beschreiben, in die Liste der Adressen, die einen Proxyserver umgehen.</span><span class="sxs-lookup"><span data-stu-id="69533-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="69533-126">Der Wert `address` des Attributs sollte ein regulärer Ausdruck sein, der eine Gruppe von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="69533-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="69533-127">Sie sollten vorsichtshalber sein, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="69533-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="69533-128">Der reguläre Ausdruck "[a-z]+\\\\.contoso .com" entspricht jedem Host in der contoso.com Domäne, aber auch jedem Host in der contoso.com.cpandl.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="69533-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="69533-129">Um nur einen Host in der domäne contoso.com abzugleichen, verwenden Sie einen\\Anker ("-"): "[a-z]+ .contoso\\.com".</span><span class="sxs-lookup"><span data-stu-id="69533-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="69533-130">Weitere Informationen zu regulären Ausdrücken finden Sie unter . [.NET Framework Reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="69533-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="69533-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="69533-131">Configuration Files</span></span>  
 <span data-ttu-id="69533-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69533-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69533-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69533-133">Example</span></span>  
 <span data-ttu-id="69533-134">Im folgenden Beispiel werden der Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="69533-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="69533-135">Die erste umgeht den Proxy für alle Server in der contoso.com Domäne. Der zweite umgeht den Proxy für alle Server, deren IP-Adresse mit 192.168 beginnt.</span><span class="sxs-lookup"><span data-stu-id="69533-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69533-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69533-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="69533-137">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="69533-137">Network Settings Schema</span></span>](index.md)
