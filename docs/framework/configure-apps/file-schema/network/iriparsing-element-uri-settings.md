---
title: <iriParsing>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698093"
---
# <a name="iriparsing-element-uri-settings"></a>\<iriParsing>-Element (URI-Einstellungen)
Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
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
|`enabled`|Gibt an, ob die IRI-Verarbeitung aktiviert ist. Der Standardwert ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die vorhandene <xref:System.Uri> Klasse wurde in .NET Framework 3,5 erweitert. 3,0 SP1 und 2,0 SP1 zur Unterstützung von International Resource Identifier (IRI) und internationalisierten Domänen Namen (IDN). Aktuelle Benutzer sehen keine Änderung des Verhaltens von .NET Framework 2,0, es sei denn, Sie aktivieren speziell IRI-und IDN-Unterstützung. Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.  
  
 Die folgenden beiden Änderungen sind erforderlich, um die Unterstützung für IRI zu aktivieren:  
  
1. Fügen Sie der Datei Machine. config im Verzeichnis .NET Framework 2,0 die folgende Zeile hinzu.  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Geben Sie an, ob die IRI-Verarbeitungs Regeln angewendet werden sollen. Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.  
  
 Durch das Aktivieren der IRI-Verarbeitung (iriising aktiviert = `true` ) erfolgt die Normalisierung und Zeichen Überprüfung gemäß den neuesten IRI-Regeln in RFC 3987. Der Standardwert ist `false` und führt normalisierungs-und Zeichen Prüfungen gemäß RFC 2396 und RFC 3986 (für IPv6-Literale) durch.  
  
### <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  
 Das folgende Beispiel zeigt eine Konfiguration, die von der- <xref:System.Uri> Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.  
  
### <a name="code"></a>Code  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
