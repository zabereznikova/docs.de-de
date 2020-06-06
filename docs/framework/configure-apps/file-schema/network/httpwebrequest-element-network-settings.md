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
ms.openlocfilehash: d33dadc14510feb00e05ca557b507b0cf8fa0dd0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087456"
---
# <a name="httpwebrequest-element-network-settings"></a>\<httpWebRequest>-Element (Netzwerkeinstellungen)
Passt Webanforderungs Parameter an.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

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
|`maximumResponseHeadersLength`|Gibt die maximale Länge eines Antwort Headers in Kilobyte an. Der Standardwert ist 64. Der Wert-1 gibt an, dass keine Größenbeschränkung für die Antwortheader festgelegt wird.|  
|`maximumErrorResponseLength`|Gibt die maximale Länge einer Fehler Antwort in Kilobyte an. Der Standardwert ist 64. Der Wert-1 gibt an, dass für die Fehler Antwort keine Größenbeschränkung festgelegt wird.|  
|`maximumUnauthorizedUploadLength`|Gibt die maximale Länge eines Uploads als Reaktion auf einen nicht autorisierten Fehlercode in Bytes an. Der Standard ist -1. Der Wert -1 gibt an, dass für den Upload keine Größenbeschränkung gilt.|  
|`useUnsafeHeaderParsing`|Gibt an, ob die unsichere Header-Verarbeitung aktiviert ist. Der Standardwert ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Bemerkungen  
 Standardmäßig erzwingt das .NET Framework nur RFC 2616 für die URI-Verarbeitung. Einige Server Antworten können Steuerzeichen in unzulässigen Feldern enthalten, die bewirken, dass die- <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode eine auslöst <xref:System.Net.WebException> . Wenn **useunsafeheaderanalysing** auf **true**festgelegt ist, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> wird in diesem Fall nicht ausgelöst. Ihre Anwendung ist jedoch für mehrere Formen von URI-analyseangriffen anfällig. Die beste Lösung besteht darin, den Server so zu ändern, dass die Antwort keine Steuerzeichen enthält.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine größer als normale maximale Header Länge angegeben wird.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [Netzwerkeinstellungsschema](index.md)
