---
title: <bypasslist>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154945"
---
# <a name="bypasslist-element-network-settings"></a>\<Bypasslist> Element (Netzwerkeinstellungen)
Stellt eine Reihe regulärer Ausdrücke bereit, die Adressen beschreiben, die keinen Proxy verwenden.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Bypasslist>**

## <a name="syntax"></a>Syntax  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Hinzufügen](add-element-for-bypasslist-network-settings.md)|Fügt der Proxyumgehungsliste eine IP-Adresse oder einen DNS-Namen hinzu.|  
|[Klar](clear-element-for-bypasslist-network-settings.md)|Löscht die Umgehungsliste.|  
|[Entfernen](remove-element-for-bypasslist-network-settings.md)|Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxyumgehungsliste.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Umgehungsliste enthält reguläre Ausdrücke, die URIs beschreiben, auf die <xref:System.Net.WebRequest> Instanzen direkt statt über den Proxyserver zugreifen.  
  
 Sie sollten vorsichtshalber sein, wenn Sie einen regulären Ausdruck für dieses Element angeben. Der reguläre Ausdruck "[a-z]+\\\\.contoso .com" entspricht jedem Host in der contoso.com Domäne, aber auch jedem Host in der contoso.com.cpandl.com Domäne. Um nur einen Host in der domäne contoso.com abzugleichen, verwenden Sie einen\\Anker ("-"): "[a-z]+ .contoso\\.com".  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter . [.NET Framework Reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden der Umgehungsliste zwei Adressen hinzugefügt. Die erste umgeht den Proxy für alle Server in der contoso.com Domäne. Der zweite umgeht den Proxy für alle Server, deren IP-Adressen mit 192.168 beginnen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
