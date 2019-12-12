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
ms.openlocfilehash: 1db0ba3b0a213de1175e6e0cee347753d2a413b7
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699616"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="b9662-102">\<add >-Element für bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b9662-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="b9662-103">Fügt der Proxy Umgehungs Liste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9662-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="b9662-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="b9662-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b9662-105">&nbsp; @ no__t-1[**@no__t -4system. net >**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b9662-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="b9662-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[**\<defaultproxy >**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b9662-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="b9662-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[**\<bypasslist >**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b9662-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="b9662-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="b9662-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9662-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9662-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9662-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9662-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9662-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9662-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9662-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9662-112">Attributes</span></span>  
  
|<span data-ttu-id="b9662-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="b9662-113">**Attribute**</span></span>|<span data-ttu-id="b9662-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b9662-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="b9662-115">**address**</span><span class="sxs-lookup"><span data-stu-id="b9662-115">**address**</span></span>|<span data-ttu-id="b9662-116">Einen regulären Ausdruck, der eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b9662-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9662-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9662-117">Child Elements</span></span>  
 <span data-ttu-id="b9662-118">Keine</span><span class="sxs-lookup"><span data-stu-id="b9662-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9662-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9662-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b9662-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="b9662-120">**Element**</span></span>|<span data-ttu-id="b9662-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b9662-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b9662-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="b9662-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="b9662-123">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9662-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9662-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9662-124">Remarks</span></span>  
 <span data-ttu-id="b9662-125">Das `add`-Element fügt reguläre Ausdrücke, die IP-Adressen oder DNS-Servernamen beschreiben, in die Liste der Adressen ein, die einen Proxy Server umgehen.</span><span class="sxs-lookup"><span data-stu-id="b9662-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="b9662-126">Der Wert des `address`-Attributs muss ein regulärer Ausdruck sein, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b9662-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="b9662-127">Sie sollten Vorsicht walten lassen, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="b9662-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="b9662-128">Der reguläre Ausdruck "[a-z] + @no__t -0.contoso\\.com" stimmt mit jedem Host in der contoso.com-Domäne überein, aber auch mit jedem Host in der contoso.com.cpandl.com-Domäne überein.</span><span class="sxs-lookup"><span data-stu-id="b9662-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="b9662-129">Um nur einen Host in der contoso.com-Domäne zu finden, verwenden Sie einen Anker ("$"): "[a-z] + @no__t -0.contoso\\.com $".</span><span class="sxs-lookup"><span data-stu-id="b9662-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="b9662-130">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [.NET Framework reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b9662-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b9662-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b9662-131">Configuration Files</span></span>  
 <span data-ttu-id="b9662-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9662-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9662-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9662-133">Example</span></span>  
 <span data-ttu-id="b9662-134">Im folgenden Beispiel werden der Umgehungs Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9662-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="b9662-135">Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adresse mit 192,168 beginnt.</span><span class="sxs-lookup"><span data-stu-id="b9662-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9662-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9662-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="b9662-137">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b9662-137">Network Settings Schema</span></span>](index.md)
