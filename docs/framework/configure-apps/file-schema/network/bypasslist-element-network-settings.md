---
title: <bypasslist>-Element (Netzwerkeinstellungen)
description: Das <bypasslist> Network settings-Element stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy in der .NET Framework verwenden.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 42b6ddf4c3d09bcf8ef0ada105cefedccc63b505
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504627"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist>-Element (Netzwerkeinstellungen)
Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a>Syntax  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[add](add-element-for-bypasslist-network-settings.md)|Fügt der Proxy Umgehungs Liste eine IP-Adresse oder einen DNS-Namen hinzu.|  
|[Löschen](clear-element-for-bypasslist-network-settings.md)|Löscht die Umgehungs Liste.|  
|[remove](remove-element-for-bypasslist-network-settings.md)|Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxy Umgehungs Liste.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Umgehungs Liste enthält reguläre Ausdrücke, die URIs beschreiben, <xref:System.Net.WebRequest> auf die Instanzen direkt anstatt über den Proxy Server zugreifen.  
  
 Sie sollten Vorsicht walten lassen, wenn Sie einen regulären Ausdruck für dieses Element angeben. Der reguläre Ausdruck "[a-z] + \\ ..................................... \\ Um nur einen Host in der contoso.com-Domäne zu finden, verwenden Sie einen Anker ("$"): "[a-z] + \\ .. \\ .  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter. [.NET Framework reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden der Umgehungs Liste zwei Adressen hinzugefügt. Der erste umgeht den Proxy für alle Server in der contoso.com-Domäne. mit dem zweiten wird der Proxy für alle Server umgangen, deren IP-Adressen mit 192,168 beginnen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
