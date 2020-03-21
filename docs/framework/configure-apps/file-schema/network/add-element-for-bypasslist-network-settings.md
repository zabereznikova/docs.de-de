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
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155076"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<Hinzufügen> Elements für Bypasslist (Netzwerkeinstellungen)
Fügt der Proxyumgehungsliste eine IP-Adresse oder einen DNS-Namen hinzu.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|**Adresse**|Ein regulärer Ausdruck, der eine IP-Adresse oder einen DNS-Namen beschreibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|Stellt eine Reihe regulärer Ausdrücke bereit, die Adressen beschreiben, die keinen Proxy verwenden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `add` Element fügt reguläre Ausdrücke ein, die IP-Adressen oder DNS-Servernamen beschreiben, in die Liste der Adressen, die einen Proxyserver umgehen.  
  
 Der Wert `address` des Attributs sollte ein regulärer Ausdruck sein, der eine Gruppe von IP-Adressen oder Hostnamen beschreibt.  
  
 Sie sollten vorsichtshalber sein, wenn Sie einen regulären Ausdruck für dieses Element angeben. Der reguläre Ausdruck "[a-z]+\\\\.contoso .com" entspricht jedem Host in der contoso.com Domäne, aber auch jedem Host in der contoso.com.cpandl.com Domäne. Um nur einen Host in der domäne contoso.com abzugleichen, verwenden Sie einen\\Anker ("-"): "[a-z]+ .contoso\\.com".  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter . [.NET Framework Reguläre Ausdrücke](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden der Umgehungsliste zwei Adressen hinzugefügt. Die erste umgeht den Proxy für alle Server in der contoso.com Domäne. Der zweite umgeht den Proxy für alle Server, deren IP-Adresse mit 192.168 beginnt.  
  
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
