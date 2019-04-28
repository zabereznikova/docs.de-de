---
title: <webRequestModules>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e5d1780a204b2e99593d51179a479845fd49e608
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704946"
---
# <a name="webrequestmodules-element-network-settings"></a>\<WebRequestModules >-Element (Netzwerkeinstellungen)
Gibt die Module zu verwenden, um Informationen aus der Hosts im Netzwerk anzufordern.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|Die Anwendung hinzugefügt ein benutzerdefinierte Webanforderungsmodul.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|Entfernt alle registrierte Webanforderungsmodulen aus der Anwendung an.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|Entfernt ein benutzerdefinierte Webanforderungsmodul aus der Anwendung an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `webRequestModules` Element registriert Nachfolger der <xref:System.Net.WebRequest> -Klasse zur Verarbeitung von Anforderungen an die Hosts im Netzwerk. Webanforderungsmodule müssen implementieren die <xref:System.Net.IWebRequestCreate> Schnittstelle.  
  
 .NET Framework enthält Webanforderungsmodule für URIs, die mit beginnen `http://`, `https://`, und `file://`. Sie können die Standardmodule nur durch Registrieren eines benutzerdefinierten Moduls in der Konfigurationsdatei überschreiben.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird das Standard-HTTP-Modul registriert. Sie sollten die Werte für die Version und ' PublicKeyToken ' machen durch die richtigen Werte für das angegebene Modul ersetzen.  
  
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
- <xref:System.Net.IWebRequestCreate>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
