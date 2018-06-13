---
title: '&lt;IriParsing&gt; Element (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f05f7e35d69f789d3ebb371689aafbc84004b732
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743302"
---
# <a name="ltiriparsinggt-element-uri-settings"></a>&lt;IriParsing&gt; Element (Uri-Einstellungen)
Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.  
  
## <a name="schema-hierarchy"></a>Schemahierarchie  
 [\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI >-Element (Uri-Einstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<IriParsing >](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|`enabled`|Gibt an, ob IRI-Analyse aktiviert ist. Der Standardwert ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.|  
  
## <a name="remarks"></a>Hinweise  
 Die vorhandene <xref:System.Uri> Klasse in .NET Framework 3.5 erweitert wurde. 3.0 SP1 und 2.0 SP1 zur Unterstützung von International Resource Identifiers (IRI) und internationale Domänennamen (IDN). Aktuellen Benutzer sehen keine Änderungen des Verhaltens gegenüber den .NET Framework 2.0, es sei denn, sie explizit IRI und IDN aktivieren unterstützen. Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.  
  
 Um die Unterstützung für IRI aktivieren, sind die folgenden zwei Änderungen erforderlich:  
  
1.  Fügen Sie die folgende Zeile auf die Datei "Machine.config" im .NET Framework 2.0-Verzeichnis  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Geben Sie an, ob die IRI-Analyse Regeln angewendet werden soll. Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.  
  
 Aktivieren die IRI-Analyse (IriParsing aktiviert = `true`) ist dies der Normalisierung und zeichenüberprüfung entsprechend der neuesten IRI Regeln in RFC 3987. Der Standardwert ist `false` und führen Sie die Normalisierung und Überprüfung gemäß RFC 2396 und RFC 3986 mit Escapezeichen (für IPv6-Literale) Zeichen.  
  
### <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse IRI-Analyse und IDN-Namen unterstützt.  
  
### <a name="code"></a>Code  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
