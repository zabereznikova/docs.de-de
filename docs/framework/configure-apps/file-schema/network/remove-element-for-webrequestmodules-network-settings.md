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
ms.openlocfilehash: c57e2849d608b1706c41beca91ff8026ebd9ca45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705024"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a>\<Entfernen Sie >-Element für WebRequestModules (Netzwerkeinstellungen)
Entfernt ein benutzerdefinierte Webanforderungsmodul aus der Anwendung an.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
\<remove>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`prefix`|Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul behandelt werden soll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die Module zu verwenden, um Informationen aus der Hosts im Netzwerk anzufordern.|  
  
## <a name="remarks"></a>Hinweise  
 Die `remove` -Element entfernt die eingetragene Webanforderungsmodul für das angegebene URI-Präfix.  
  
 Der Wert für die `prefix` Attribut muss die führenden Zeichen eine gültige URI sein – z. B. "`http`", oder "`http://www.contoso.com`".  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird das vorhandene Webanforderungsmodul für HTTP und registriert dann ein neues benutzerdefinierte Webanforderungsmodul für HTTP-Anforderungen an `www.contoso.com`.
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.WebRequest>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
