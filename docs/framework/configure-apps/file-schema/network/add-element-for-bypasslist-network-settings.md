---
title: "&lt;Hinzufügen&gt; Bypasslist (Network Settings)-Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: bed3abd5522b748a2bd24ba03c7be5d991deae9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-bypasslist-network-settings"></a>&lt;Hinzufügen&gt; Bypasslist (Network Settings)-Element
Fügt eine IP-Adresse oder einen DNS-Namen, die Proxyumgehungsliste.  
  
 \<configuration>  
\<System.NET >  
\<DefaultProxy >  
\<BypassList >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|**address**|Ein regulärer Ausdruck, die eine IP-Adresse oder einen DNS-Namen beschreibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[BypassList](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Stellt einen Satz von regulären Ausdrücken, die Beschreibung der Adressen, die keinen Proxy verwenden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `add` -Element fügt reguläre Ausdrücke, die IP-Adressen oder DNS-Servernamen, um die Liste der Adressen, die einen Proxyserver umgehen beschreibt.  
  
 Der Wert, der die `address` Attribut muss ein regulärer Ausdruck, der einen Satz von IP-Adressen oder Hostnamen beschreibt.  
  
 Sie sollten Vorsicht walten, wenn Sie für dieses Element einen regulären Ausdruck angeben. Der reguläre Ausdruck "[a-Z] +\\.contoso\\.com" entspricht, die jedem host in der Domäne "contoso.com", sondern auch mit jedem Host in der Domäne contoso.com.cpandl.com überein. Um nur einen Host in der Domäne "contoso.com" zu vergleichen, verwenden Sie einen Anker ("$"): "[a-Z] +\\.contoso\\".com "$".  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird die Umgehungsliste zwei Adressen hinzugefügt. Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite umgeht den Proxy für alle Server, dessen IP-Adresse beginnt, mit 192.168.  
  
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
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
