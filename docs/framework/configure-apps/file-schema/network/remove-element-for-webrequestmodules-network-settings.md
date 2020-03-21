---
title: <remove>-Element für webRequestModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154724"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a>\<Entfernen> Element für webRequestModules (Netzwerkeinstellungen)
Entfernt ein benutzerdefiniertes Webanforderungsmodul aus der Anwendung.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`prefix`|Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul verarbeitet werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Gibt Module an, die zum Anfordern von Informationen von Netzwerkhosts verwendet werden sollen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `remove` Element entfernt das registrierte Webanforderungsmodul für das angegebene URI-Präfix.  
  
 Der Wert `prefix` für das Attribut sollte die führenden Zeichen eines`http`gültigen URI`http://www.contoso.com`sein , z. B. " ", oder " ".  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird das vorhandene Webanforderungsmodul für HTTP entfernt und anschließend `www.contoso.com`ein neues benutzerdefiniertes Webanforderungsmodul für HTTP-Anforderungen an registriert.
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebRequest>
- [Netzwerkeinstellungsschema](index.md)
