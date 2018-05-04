---
title: '&lt;Hinzufügen&gt; WebRequestModules (Network Settings)-Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 921f5f2bfda1a19d022d3f3f4131e3653fd17ea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a>&lt;Hinzufügen&gt; WebRequestModules (Network Settings)-Element
Fügt eine benutzerdefinierte Webmodul der Anforderung an die Anwendung an.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`prefix`|Das URI-Präfix für Anforderungen, die von dieser Anforderung Webmodul behandelt werden soll.|  
|`type`|Den vollqualifizierten Typnamen (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und der Name der Assembly (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die diese Web-Request-Modul implementiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die Module zu verwenden, um Informationen von Netzwerkhosts anfordern.|  
  
## <a name="remarks"></a>Hinweise  
 Die `prefix` Attribut definiert die URI-Präfix, das das angegebene Modul der Web-Anforderung verwendet. Anforderung Webmodule werden in der Regel zum Behandeln eines bestimmten Protokolls, z. B. HTTP oder FTP, registriert, jedoch können registriert werden, um eine Anforderung für einen bestimmten Server oder einen Pfad auf einem Server zu behandeln.  
  
 Die Anforderung Webmodul wird erstellt, wenn ein übereinstimmendes URI-Präfix an übergeben wird die <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> Methode.  
  
 Der Wert für die `prefix` Attribut muss die ersten Zeichen ein gültiger URI – z. B. "http", oder "http://www.contoso.com".  
  
 Der Wert für die `type` Attribut muss eine gültige Typnamen und die entsprechenden Assemblynamen an, die durch ein Komma getrennt werden.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel registriert ein benutzerdefiniertes Web-Request-Modul für HTTP. Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.WebRequest>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
