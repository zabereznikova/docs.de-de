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
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674622"
---
# <a name="bypasslist-element-network-settings"></a>\<BypassList >-Element (Netzwerkeinstellungen)
Bietet eine Reihe von regulären Ausdrücken, die Adressen beschreiben, die einen Proxy nicht verwenden.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
  
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
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Fügt eine IP-Adresse oder DNS-Namen, der Proxyumgehungsliste enthalten an.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Löscht die Bypass-Liste.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Entfernt eine IP-Adresse oder DNS-Namen, aus der Proxyumgehungsliste enthalten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="remarks"></a>Hinweise  
 Die Bypass-Liste enthält reguläre Ausdrücke, die URIs beschreiben, <xref:System.Net.WebRequest> Instanzen, die direkt anstelle von über den Proxyserver zuzugreifen.  
  
 Sie sollten Vorsicht walten, wenn Sie einen regulären Ausdruck für dieses Element angeben. Der reguläre Ausdruck "[a-Z] +\\.contoso\\.com" entspricht, die jedem host in der Domäne "contoso.com", sondern auch mit jedem Host in der Domäne contoso.com.cpandl.com überein. Um nur einen Host in der Domäne "contoso.com" zu vergleichen, verwenden Sie ein Ankerelement ("$"): "[a-Z] +\\.contoso\\.com$".  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird der Umgehungsliste zwei Adressen hinzugefügt. Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite wird der Proxy für alle Server, deren IP-Adressen beginnen mit 192.168. umgangen.  
  
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
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
