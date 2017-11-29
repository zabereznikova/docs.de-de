---
title: '&lt;Deaktivieren Sie&gt; Bypasslist (Network Settings)-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5ee20b9177d519010c40351e335973dce10256f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="bb0d2-102">&lt;Deaktivieren Sie&gt; Bypasslist (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="bb0d2-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="bb0d2-103">Löscht die Proxyumgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="bb0d2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb0d2-104">\<configuration></span></span>  
<span data-ttu-id="bb0d2-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="bb0d2-105">\<system.net></span></span>  
<span data-ttu-id="bb0d2-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="bb0d2-106">\<defaultProxy></span></span>  
<span data-ttu-id="bb0d2-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="bb0d2-107">\<bypasslist></span></span>  
<span data-ttu-id="bb0d2-108">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="bb0d2-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb0d2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb0d2-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb0d2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb0d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bb0d2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb0d2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb0d2-112">Attributes</span></span>  
 <span data-ttu-id="bb0d2-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb0d2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb0d2-114">Child Elements</span></span>  
 <span data-ttu-id="bb0d2-115">Keine</span><span class="sxs-lookup"><span data-stu-id="bb0d2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb0d2-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb0d2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bb0d2-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="bb0d2-117">**Element**</span></span>|<span data-ttu-id="bb0d2-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bb0d2-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bb0d2-119">BypassList</span><span class="sxs-lookup"><span data-stu-id="bb0d2-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="bb0d2-120">Stellt einen Satz von regulären Ausdrücken, die Beschreibung der Adressen, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb0d2-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb0d2-121">Remarks</span></span>  
 <span data-ttu-id="bb0d2-122">Die `clear` -Element löscht alle Einträge aus der Umgehungsliste.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bb0d2-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="bb0d2-123">Configuration Files</span></span>  
 <span data-ttu-id="bb0d2-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb0d2-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb0d2-125">Example</span></span>  
 <span data-ttu-id="bb0d2-126">Im folgenden Beispiel löscht die Bypass-Liste und klicken Sie dann die Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="bb0d2-127">Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite umgeht den Proxy für alle Server, dessen IP-Adresse beginnt, mit 192.168.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb0d2-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb0d2-128">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="bb0d2-129">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bb0d2-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
