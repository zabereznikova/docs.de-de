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
ms.openlocfilehash: 99c18bd5b779845d52831b4a9591eaf4d5e5530b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920960"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="1dd6b-102">\<Entfernen von >-Element für bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1dd6b-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="1dd6b-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

<span data-ttu-id="1dd6b-104">\<Konfigurations > </span><span class="sxs-lookup"><span data-stu-id="1dd6b-104">\<configuration></span></span>\
<span data-ttu-id="1dd6b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1dd6b-105">\<system.net></span></span>\
<span data-ttu-id="1dd6b-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="1dd6b-106">\<defaultProxy></span></span>\
<span data-ttu-id="1dd6b-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="1dd6b-107">\<bypasslist></span></span>\
<span data-ttu-id="1dd6b-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="1dd6b-108">\<remove></span></span>

## <a name="syntax"></a><span data-ttu-id="1dd6b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1dd6b-109">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1dd6b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1dd6b-110">Attributes and Elements</span></span>

<span data-ttu-id="1dd6b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1dd6b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1dd6b-112">Attributes</span></span>

|<span data-ttu-id="1dd6b-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="1dd6b-113">**Attribute**</span></span>|<span data-ttu-id="1dd6b-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1dd6b-114">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="1dd6b-115">Einen regulären Ausdruck, der eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-115">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1dd6b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1dd6b-116">Child Elements</span></span>

<span data-ttu-id="1dd6b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="1dd6b-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1dd6b-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1dd6b-118">Parent Elements</span></span>

|<span data-ttu-id="1dd6b-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="1dd6b-119">**Element**</span></span>|<span data-ttu-id="1dd6b-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1dd6b-120">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="1dd6b-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="1dd6b-121">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="1dd6b-122">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1dd6b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1dd6b-123">Remarks</span></span>

<span data-ttu-id="1dd6b-124">Das `remove` -Element entfernt reguläre Ausdrücke, in denen IP-Adressen oder DNS-Servernamen aus der Liste der Adressen, die einen Proxy Server umgehen, beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="1dd6b-125">Die Adressen wurden zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="1dd6b-126">Der Wert für das `address` -Attribut muss ein regulärer Ausdruck sein, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="1dd6b-127">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [.NET Framework reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1dd6b-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="1dd6b-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="1dd6b-128">Configuration Files</span></span>

<span data-ttu-id="1dd6b-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="1dd6b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1dd6b-130">Example</span></span>

<span data-ttu-id="1dd6b-131">Im folgenden Beispiel werden alle vorherigen Definitionen für die Domäne Adventure-Works.com entfernt und dann der Umgehungs Liste die contoso.com-Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1dd6b-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1dd6b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dd6b-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="1dd6b-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1dd6b-133">Network Settings Schema</span></span>](index.md)
