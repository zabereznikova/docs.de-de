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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155023"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<add>-Element für webRequestModules (Netzwerkeinstellungen)
Fügt der Anwendung ein benutzerdefiniertes Webanforderungs Modul hinzu.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

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
|`prefix`|Das URI-Präfix für Anforderungen, die von diesem Webanforderungs Modul behandelt werden.|  
|`type`|Der voll qualifizierte Typname (angegeben durch die- <xref:System.Type.FullName%2A> Eigenschaft) und der AssemblyName (angegeben durch die- <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, das dieses Webanforderungs Modul implementiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `prefix` Attribut definiert das URI-Präfix, das das angegebene Webanforderungs Modul verwendet. Webanforderungs Module sind in der Regel für die Verarbeitung eines bestimmten Protokolls registriert, z. b. http oder FTP, können jedoch registriert werden, um eine Anforderung an einen bestimmten Server oder Pfad auf einem Server zu verarbeiten.  
  
 Das Webanforderungs Modul wird erstellt, wenn ein URI-übereinstimmendes Präfix an die Methode übermittelt wird <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> .  
  
 Der Wert für das- `prefix` Attribut muss die führenden Zeichen eines gültigen URI sein. Zum Beispiel: `http` oder `http://www.contoso.com`.
  
 Der Wert für das `type` -Attribut muss ein gültiger Typname und der zugehörige AssemblyName sein, getrennt durch ein Komma.
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein benutzerdefiniertes Webanforderungs Modul für http registriert. Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.  
  
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
