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
ms.openlocfilehash: 2ad6b16370f600299439d2e810dfefa1b5fa3c06
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087531"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="916f5-102">\<>-Element für bypasslist (Netzwerkeinstellungen) löschen.</span><span class="sxs-lookup"><span data-stu-id="916f5-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="916f5-103">Löscht die Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="916f5-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="916f5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="916f5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="916f5-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="916f5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="916f5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="916f5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="916f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BypassList >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="916f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="916f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Löschen >**</span><span class="sxs-lookup"><span data-stu-id="916f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="916f5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="916f5-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="916f5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="916f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="916f5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="916f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="916f5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="916f5-112">Attributes</span></span>  
 <span data-ttu-id="916f5-113">Keine</span><span class="sxs-lookup"><span data-stu-id="916f5-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="916f5-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="916f5-114">Child Elements</span></span>  
 <span data-ttu-id="916f5-115">Keine</span><span class="sxs-lookup"><span data-stu-id="916f5-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="916f5-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="916f5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="916f5-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="916f5-117">**Element**</span></span>|<span data-ttu-id="916f5-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="916f5-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="916f5-119">BypassList</span><span class="sxs-lookup"><span data-stu-id="916f5-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="916f5-120">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="916f5-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="916f5-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="916f5-121">Remarks</span></span>  
 <span data-ttu-id="916f5-122">Das `clear`-Element löscht alle Einträge aus der Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="916f5-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="916f5-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="916f5-123">Configuration Files</span></span>  
 <span data-ttu-id="916f5-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="916f5-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="916f5-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="916f5-125">Example</span></span>  
 <span data-ttu-id="916f5-126">Im folgenden Beispiel wird die Umgehungs Liste gelöscht und dann der Umgehungs Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="916f5-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="916f5-127">Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adresse mit 192,168 beginnt.</span><span class="sxs-lookup"><span data-stu-id="916f5-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="916f5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="916f5-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="916f5-129">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="916f5-129">Network Settings Schema</span></span>](index.md)
