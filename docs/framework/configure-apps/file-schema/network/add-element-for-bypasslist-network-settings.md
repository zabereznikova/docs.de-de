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
ms.openlocfilehash: 702aa8ccefcdddee1ffc5a7519a4f955b1dc5dfb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265661"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="34cb8-102">\<Hinzufügen >-Element für Bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="34cb8-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="34cb8-103">Fügt eine IP-Adresse oder DNS-Namen, der Proxyumgehungsliste enthalten an.</span><span class="sxs-lookup"><span data-stu-id="34cb8-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="34cb8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="34cb8-104">\<configuration></span></span>  
<span data-ttu-id="34cb8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="34cb8-105">\<system.net></span></span>  
<span data-ttu-id="34cb8-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="34cb8-106">\<defaultProxy></span></span>  
<span data-ttu-id="34cb8-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="34cb8-107">\<bypasslist></span></span>  
<span data-ttu-id="34cb8-108">\<add></span><span class="sxs-lookup"><span data-stu-id="34cb8-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34cb8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="34cb8-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34cb8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34cb8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="34cb8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34cb8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34cb8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="34cb8-112">Attributes</span></span>  
  
|<span data-ttu-id="34cb8-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="34cb8-113">**Attribute**</span></span>|<span data-ttu-id="34cb8-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="34cb8-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="34cb8-115">**address**</span><span class="sxs-lookup"><span data-stu-id="34cb8-115">**address**</span></span>|<span data-ttu-id="34cb8-116">Ein regulärer Ausdruck, ein IP-Adresse oder DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="34cb8-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34cb8-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34cb8-117">Child Elements</span></span>  
 <span data-ttu-id="34cb8-118">Keine</span><span class="sxs-lookup"><span data-stu-id="34cb8-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34cb8-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34cb8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="34cb8-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="34cb8-120">**Element**</span></span>|<span data-ttu-id="34cb8-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="34cb8-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="34cb8-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="34cb8-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="34cb8-123">Bietet eine Reihe von regulären Ausdrücken, die Adressen beschreiben, die einen Proxy nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="34cb8-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34cb8-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34cb8-124">Remarks</span></span>  
 <span data-ttu-id="34cb8-125">Die `add` -Element fügt reguläre Ausdrücke, die beschreiben, IP-Adressen oder DNS-Servernamen zur Liste der Adressen, die einen Proxyserver zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="34cb8-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="34cb8-126">Der Wert des der `address` Attribut sollte sein, einen regulären Ausdruck, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="34cb8-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="34cb8-127">Sie sollten Vorsicht walten, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="34cb8-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="34cb8-128">Der reguläre Ausdruck "[a-Z] +\\.contoso\\.com" entspricht, die jedem host in der Domäne "contoso.com", sondern auch mit jedem Host in der Domäne contoso.com.cpandl.com überein.</span><span class="sxs-lookup"><span data-stu-id="34cb8-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="34cb8-129">Um nur einen Host in der Domäne "contoso.com" zu vergleichen, verwenden Sie ein Ankerelement ("$"): "[a-Z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="34cb8-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="34cb8-130">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="34cb8-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="34cb8-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="34cb8-131">Configuration Files</span></span>  
 <span data-ttu-id="34cb8-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34cb8-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34cb8-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34cb8-133">Example</span></span>  
 <span data-ttu-id="34cb8-134">Im folgende Beispiel wird der Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="34cb8-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="34cb8-135">Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite wird der Proxy für alle Server, dessen IP-Adresse beginnt, mit 192.168. umgangen.</span><span class="sxs-lookup"><span data-stu-id="34cb8-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34cb8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34cb8-136">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="34cb8-137">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="34cb8-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
