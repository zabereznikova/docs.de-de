---
title: <add>-Element für webRequestModules (Netzwerkeinstellungen)
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
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155023"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<Hinzufügen> Elements für webRequestModules (Netzwerkeinstellungen)
Fügt der Anwendung ein benutzerdefiniertes Webanforderungsmodul hinzu.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**

## <a name="syntax"></a>Syntax  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`prefix`|Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul verarbeitet werden.|  
|`type`|Der vollqualifizierte Typname (durch die <xref:System.Type.FullName%2A> Eigenschaft angegeben) und <xref:System.Reflection.Assembly.FullName%2A> der Assemblyname (durch die Eigenschaft angegeben), getrennt durch ein Komma, das dieses Webanforderungsmodul implementiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Gibt Module an, die zum Anfordern von Informationen von Netzwerkhosts verwendet werden sollen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `prefix` Attribut definiert das URI-Präfix, das das angegebene Webanforderungsmodul verwendet. Webanforderungsmodule werden in der Regel für die Verarbeitung eines bestimmten Protokolls, z. B. HTTP oder FTP, registriert, können jedoch registriert werden, um eine Anforderung an einen bestimmten Server oder Pfad auf einem Server zu verarbeiten.  
  
 Das Webanforderungsmodul wird erstellt, wenn ein <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> URI-Abgleichspräfix an die Methode übergeben wird.  
  
 Der Wert `prefix` für das Attribut sollte die führenden Zeichen eines gültigen URI sein. Zum Beispiel: `http` oder `http://www.contoso.com`.
  
 Der Wert `type` für das Attribut sollte ein gültiger Typname und ein entsprechender Assemblyname sein, der durch ein Komma getrennt ist.
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein benutzerdefiniertes Webanforderungsmodul für HTTP registriert. Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebRequest>
- [Netzwerkeinstellungsschema](index.md)
