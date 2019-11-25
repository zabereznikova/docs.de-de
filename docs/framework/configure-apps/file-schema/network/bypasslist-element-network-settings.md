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
ms.openlocfilehash: 7a6c1282c9ca8381d2dbb21ffdc82f95732c42b3
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087521"
---
# <a name="bypasslist-element-network-settings"></a>\<BypassList >-Element (Netzwerkeinstellungen)
Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<BypassList >**

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
 Die Umgehungs Liste enthält reguläre Ausdrücke, mit denen URIs beschrieben werden, die <xref:System.Net.WebRequest> Instanzen direkt anstatt über den Proxy Server auf die Instanzen zugreifen.  
  
 Sie sollten Vorsicht walten lassen, wenn Sie einen regulären Ausdruck für dieses Element angeben. Der reguläre Ausdruck "[a-z] +\\.\\. com" stimmt mit jedem Host in der contoso.com-Domäne überein, aber auch mit jedem Host in der contoso.com.cpandl.com-Domäne überein. Um nur einen Host in der contoso.com-Domäne zu finden, verwenden Sie einen Anker ("$"): "[a-z] +\\.\\. com $".  
  
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
