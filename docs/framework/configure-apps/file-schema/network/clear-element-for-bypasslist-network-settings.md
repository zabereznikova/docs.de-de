---
title: '&lt;Deaktivieren Sie&gt; -Element für Bypasslist (Netzwerkeinstellungen)'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ca6c8e9334bdfcdf4d79c5a91612ee117445d9cb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47237410"
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a>&lt;Deaktivieren Sie&gt; -Element für Bypasslist (Netzwerkeinstellungen)
Löscht der Proxyumgehungsliste enthalten.  
  
 \<configuration>  
\<system.net>  
\<DefaultProxy >  
\<BypassList >  
\<Deaktivieren Sie >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[BypassList](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Bietet eine Reihe von regulären Ausdrücken, die Adressen beschreiben, die einen Proxy nicht verwenden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `clear` Element löscht alle Einträge in der Umgehungsliste aufgeführt.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel löscht die Bypass-Liste und klicken Sie dann die Bypass-Liste zwei Adressen hinzugefügt. Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite wird der Proxy für alle Server, dessen IP-Adresse beginnt, mit 192.168. umgangen.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
