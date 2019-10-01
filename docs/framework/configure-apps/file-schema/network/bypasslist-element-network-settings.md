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
ms.openlocfilehash: 1dda43be8c0e0c94bdf7b57b67aa4d403b547f97
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699539"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist >-Element (Netzwerkeinstellungen)
Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultproxy >** ](defaultproxy-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<bypasslist >**  
  
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
|[clear](clear-element-for-bypasslist-network-settings.md)|Löscht die Umgehungs Liste.|  
|[remove](remove-element-for-bypasslist-network-settings.md)|Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxy Umgehungs Liste.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="remarks"></a>Hinweise  
 Die Umgehungs Liste enthält reguläre Ausdrücke, in denen URIs beschrieben werden, auf die <xref:System.Net.WebRequest>-Instanzen direkt anstatt über den Proxy Server zugreifen.  
  
 Sie sollten Vorsicht walten lassen, wenn Sie einen regulären Ausdruck für dieses Element angeben. Der reguläre Ausdruck "[a-z] + @no__t -0.contoso\\.com" stimmt mit jedem Host in der contoso.com-Domäne überein, aber auch mit jedem Host in der contoso.com.cpandl.com-Domäne überein. Um nur einen Host in der contoso.com-Domäne zu finden, verwenden Sie einen Anker ("$"): "[a-z] + @no__t -0.contoso\\.com $".  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
