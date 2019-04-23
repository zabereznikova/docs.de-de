---
title: <httpWebRequest>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 722b2f726c9085f6dee6bad82044da3011b98702
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169298"
---
# <a name="httpwebrequest-element-network-settings"></a>\<HttpWebRequest >-Element (Netzwerkeinstellungen)
Passt die Web-Anforderungsparameter.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<httpWebRequest>  
  
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
|`maximumResponseHeadersLength`|Gibt die maximale Länge des Antwortheaders in Kilobyte an. Der Standard ist 64. Der Wert-1 gibt an, dass keine größenbeschränkung für die Header der Antwort festgelegt werden, wird.|  
|`maximumErrorResponseLength`|Gibt die maximale Länge einer Fehlerantwort in Kilobyte an. Der Standard ist 64. Der Wert-1 gibt an, dass keine größenbeschränkung für die Fehlerantwort verhängt wird.|  
|`maximumUnauthorizedUploadLength`|Gibt die maximale Länge eines Uploads als Antwort auf einen nicht autorisierten Fehlercode in Byte an. Der Standard ist -1. Der Wert-1 gibt an, dass für den Upload keine größenbeschränkung festgelegt werden wird.|  
|`useUnsafeHeaderParsing`|Gibt an, ob unsichere Headeranalyse aktiviert ist. Der Standardwert ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig erzwingt .NET Framework RFC 2616 ausschließlich für die URI-Analyse. Einige Serverantworten können Steuerzeichen enthalten, in einem Feld unzulässigen, dadurch wird die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode zum Auslösen einer <xref:System.Net.WebException>. Wenn **UseUnsafeHeaderParsing** nastaven NA hodnotu **"true"**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> in diesem Fall jedoch keine Ausnahme auslöst, wird Ihre Anwendung verschiedene Formen des URI-Analyse-Angriffe anfällig. Die beste Lösung ist zum Ändern des Servers, damit die Antwort keine Steuerzeichen berücksichtigt werden.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen größeren angeben als die normale maximale Headerlänge.  
  
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

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
