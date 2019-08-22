---
title: <clear>-Element für bypasslist (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: e5305d9aed09b6c4d1ad4201e5e08e007a14c7c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664187"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="dea6d-102">\<Löschen von >-Element für bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dea6d-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="dea6d-103">Löscht die Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="dea6d-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="dea6d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dea6d-104">\<configuration></span></span>  
<span data-ttu-id="dea6d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="dea6d-105">\<system.net></span></span>  
<span data-ttu-id="dea6d-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="dea6d-106">\<defaultProxy></span></span>  
<span data-ttu-id="dea6d-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="dea6d-107">\<bypasslist></span></span>  
<span data-ttu-id="dea6d-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="dea6d-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dea6d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dea6d-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dea6d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dea6d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dea6d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dea6d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dea6d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="dea6d-112">Attributes</span></span>  
 <span data-ttu-id="dea6d-113">Keine</span><span class="sxs-lookup"><span data-stu-id="dea6d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dea6d-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dea6d-114">Child Elements</span></span>  
 <span data-ttu-id="dea6d-115">Keine</span><span class="sxs-lookup"><span data-stu-id="dea6d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dea6d-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dea6d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dea6d-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="dea6d-117">**Element**</span></span>|<span data-ttu-id="dea6d-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dea6d-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dea6d-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="dea6d-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="dea6d-120">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="dea6d-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dea6d-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dea6d-121">Remarks</span></span>  
 <span data-ttu-id="dea6d-122">Das `clear` -Element löscht alle Einträge aus der Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="dea6d-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dea6d-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="dea6d-123">Configuration Files</span></span>  
 <span data-ttu-id="dea6d-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dea6d-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dea6d-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dea6d-125">Example</span></span>  
 <span data-ttu-id="dea6d-126">Im folgenden Beispiel wird die Umgehungs Liste gelöscht und dann der Umgehungs Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dea6d-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="dea6d-127">Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adresse mit 192,168 beginnt.</span><span class="sxs-lookup"><span data-stu-id="dea6d-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="dea6d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dea6d-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="dea6d-129">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dea6d-129">Network Settings Schema</span></span>](index.md)
