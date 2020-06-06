---
title: <remove>-Element für bypasslist (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697897"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="980de-102">\<remove>-Element für bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="980de-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="980de-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="980de-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  

## <a name="syntax"></a><span data-ttu-id="980de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="980de-104">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="980de-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="980de-105">Attributes and Elements</span></span>

<span data-ttu-id="980de-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="980de-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="980de-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="980de-107">Attributes</span></span>

|<span data-ttu-id="980de-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="980de-108">**Attribute**</span></span>|<span data-ttu-id="980de-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="980de-109">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="980de-110">Einen regulären Ausdruck, der eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="980de-110">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="980de-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="980de-111">Child Elements</span></span>

<span data-ttu-id="980de-112">Keine</span><span class="sxs-lookup"><span data-stu-id="980de-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="980de-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="980de-113">Parent Elements</span></span>

|<span data-ttu-id="980de-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="980de-114">**Element**</span></span>|<span data-ttu-id="980de-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="980de-115">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="980de-116">bypasslist</span><span class="sxs-lookup"><span data-stu-id="980de-116">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="980de-117">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="980de-117">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="980de-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="980de-118">Remarks</span></span>

<span data-ttu-id="980de-119">Das `remove` -Element entfernt reguläre Ausdrücke, in denen IP-Adressen oder DNS-Servernamen aus der Liste der Adressen, die einen Proxy Server umgehen, beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="980de-119">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="980de-120">Die Adressen wurden zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert.</span><span class="sxs-lookup"><span data-stu-id="980de-120">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="980de-121">Der Wert für das `address` -Attribut muss ein regulärer Ausdruck sein, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="980de-121">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="980de-122">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [.NET Framework reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="980de-122">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="980de-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="980de-123">Configuration Files</span></span>

<span data-ttu-id="980de-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="980de-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="980de-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="980de-125">Example</span></span>

<span data-ttu-id="980de-126">Im folgenden Beispiel werden alle vorherigen Definitionen für die Domäne Adventure-Works.com entfernt und dann der Umgehungs Liste die contoso.com-Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="980de-126">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="980de-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="980de-127">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="980de-128">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="980de-128">Network Settings Schema</span></span>](index.md)
