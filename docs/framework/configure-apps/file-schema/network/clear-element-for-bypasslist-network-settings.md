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
ms.openlocfilehash: 96cef2dff3156e49a93be818230c83370dab5264
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185860"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="7b610-102">\<clear>-Element für bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7b610-102">\<clear> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="7b610-103">Löscht die Proxy Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="7b610-103">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="7b610-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b610-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b610-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b610-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7b610-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b610-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b610-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b610-107">Attributes</span></span>  

 <span data-ttu-id="7b610-108">Keine</span><span class="sxs-lookup"><span data-stu-id="7b610-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7b610-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b610-109">Child Elements</span></span>  

 <span data-ttu-id="7b610-110">Keine</span><span class="sxs-lookup"><span data-stu-id="7b610-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b610-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b610-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7b610-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="7b610-112">**Element**</span></span>|<span data-ttu-id="7b610-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7b610-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7b610-114">bypasslist</span><span class="sxs-lookup"><span data-stu-id="7b610-114">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="7b610-115">Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b610-115">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b610-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7b610-116">Remarks</span></span>  

 <span data-ttu-id="7b610-117">Das- `clear` Element löscht alle Einträge aus der Umgehungs Liste.</span><span class="sxs-lookup"><span data-stu-id="7b610-117">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7b610-118">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="7b610-118">Configuration Files</span></span>  

 <span data-ttu-id="7b610-119">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b610-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b610-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b610-120">Example</span></span>  

 <span data-ttu-id="7b610-121">Im folgenden Beispiel wird die Umgehungs Liste gelöscht und dann der Umgehungs Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b610-121">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="7b610-122">Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adresse mit 192,168 beginnt.</span><span class="sxs-lookup"><span data-stu-id="7b610-122">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7b610-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b610-123">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="7b610-124">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7b610-124">Network Settings Schema</span></span>](index.md)
