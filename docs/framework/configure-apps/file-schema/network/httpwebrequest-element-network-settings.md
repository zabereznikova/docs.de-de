---
title: '&lt;HttpWebRequest&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0a4490870cb12ff221f75b043f01baad9b5c7c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lthttpwebrequestgt-element-network-settings"></a>&lt;HttpWebRequest&gt; -Element (Netzwerkeinstellungen)
Passt die Anforderungsparameter werden Web an.  
  
 \<configuration>  
\<System.NET >  
\<Einstellungen >  
\<HttpWebRequest >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Gibt die maximale Länge des Antwortheaders in Kilobyte an. Der Standard ist 64. Der Wert-1 gibt an, dass keine größenbeschränkung für die Antwortheader auferlegt werden wird.|  
|`maximumErrorResponseLength`|Gibt die maximale Länge einer Fehlerantwort in Kilobyte an. Der Standard ist 64. Der Wert-1 gibt an, dass keine größenbeschränkung für die Fehlerantwort auferlegt werden wird.|  
|`maximumUnauthorizedUploadLength`|Gibt die maximale Länge eines Uploads als Antwort auf einen nicht autorisierten Fehlercode in Bytes an. Der Standard ist -1. Der Wert-1 gibt an, dass keine größenbeschränkung für den Upload auferlegt werden wird.|  
|`useUnsafeHeaderParsing`|Gibt an, ob unsichere Headeranalyse aktiviert ist. Der Standardwert ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Einstellungen](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig setzt .NET Framework RFC 2616 streng für die Analyse von URI. Einige Serverantworten enthalten möglicherweise Steuerzeichen in unzulässigen Feldern, wodurch die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode zum Auslösen einer <xref:System.Net.WebException>. Wenn **UseUnsafeHeaderParsing** festgelegt ist, um **"true"**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> in diesem Fall jedoch keine Ausnahme auslöst, wird Ihre Anwendung mehrere Typen von URI Analyse Angriffe anfällig sein. Die beste Lösung ist auf den Server ändern, sodass die Antwort keine Steuerzeichen enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie eine größere als normale maximale Headergröße Länge.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
