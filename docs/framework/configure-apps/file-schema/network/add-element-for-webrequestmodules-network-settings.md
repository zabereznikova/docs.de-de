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
ms.openlocfilehash: 4c1116c088c12ad3859714c8d75704d0156c12f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705141"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<Hinzufügen >-Element für WebRequestModules (Netzwerkeinstellungen)
Die Anwendung hinzugefügt ein benutzerdefinierte Webanforderungsmodul.  
  
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
|`prefix`|Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul behandelt werden soll.|  
|`type`|Der vollqualifizierte Name (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und den Assemblynamen (erkennbar die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die diese Webanforderungsmodul implementiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die Module zu verwenden, um Informationen aus der Hosts im Netzwerk anzufordern.|  
  
## <a name="remarks"></a>Hinweise  
 Die `prefix` Attribut definiert die URI-Präfix, das das angegebene Webanforderungsmodul verwendet. Webanforderungsmodule sind in der Regel registriert ein bestimmtes Protokoll wie HTTP oder FTP, jedoch können registriert werden, um eine Anforderung an einen bestimmten Server oder den Pfad auf einem Server zu behandeln.  
  
 Die Webanforderungsmodul wird erstellt, wenn ein übereinstimmendes URI-Präfix zu übergeben, wird die <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> Methode.  
  
 Der Wert für die `prefix` Attribut sollte die ersten Zeichen ein gültiger URI sein. Beispielsweise `http` oder `http://www.contoso.com`.
  
 Der Wert für die `type` Attribut sollte einen gültigen Typnamen und den entsprechenden Assemblynamen, die durch ein Komma getrennt sein.
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel registriert ein benutzerdefinierte Webanforderungsmodul für HTTP an. Sie sollten die Werte für die Version und ' PublicKeyToken ' machen durch die richtigen Werte für das angegebene Modul ersetzen.  
  
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

- <xref:System.Net.WebRequest>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
