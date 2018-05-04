---
title: '&lt;Entfernen Sie&gt; Bypasslist (Network Settings)-Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5c7918048743d53d8523ec399d1a11c67152a2bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a>&lt;Entfernen Sie&gt; Bypasslist (Network Settings)-Element
Entfernt eine IP-Adresse oder einen DNS-Namen aus der Proxyumgehungsliste.  
  
 \<configuration>  
\<system.net>  
\<DefaultProxy >  
\<BypassList >  
\<remove>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`address`|Ein regulärer Ausdruck, die eine IP-Adresse oder einen DNS-Namen beschreibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[BypassList](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Stellt einen Satz von regulären Ausdrücken, die Beschreibung der Adressen, die keinen Proxy verwenden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `remove` -Element entfernt reguläre Ausdrücke, die IP-Adressen oder DNS-Servernamen aus der Liste der Adressen, die einen Proxyserver umgehen beschreibt. Die Adressen wurden früher in der Konfigurationsdatei oder auf einer höheren Ebene in der Hierarchie definiert.  
  
 Der Wert für die `address` Attribut muss ein regulärer Ausdruck, der einen Satz von IP-Adressen oder Hostnamen beschreibt.  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel vorherige Definition für die Domäne Adventure-works.com entfernt und anschließend die Umgehungsliste der Domäne "contoso.com" hinzugefügt.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
