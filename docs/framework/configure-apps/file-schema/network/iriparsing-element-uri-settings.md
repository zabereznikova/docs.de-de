---
title: "&lt;iriParsing&gt;-Element (Uri-Einstellungen) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;iriParsing&gt;-Element (Uri-Einstellungen)
Gibt an, ob IRI\-Analysen \(International Resource Identifier\) auf einen <xref:System.Uri> angewendet werden sollen und ob IRI\-Analyseregeln beachtet werden sollen.  
  
## Schemahierarchie  
 [\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri\>\-Element \(Uri\-Einstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<iriParsing\>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## Syntax  
  
```  
<idn  
  enabled="true|false"  
/idn>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|`enabled`|Gibt an, ob die IRI\-Analyse aktiviert ist.  Der Standardwert ist `false`.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie .NET Framework durch URIs \(Uniform Resource Identifier\) ausgedrückte Webadressen behandelt.|  
  
## Hinweise  
 Die vorhandene <xref:System.Uri>\-Klasse wurde in .NET Framework 3.5, 3.0 SP1 und 2.0 SP1 so erweitert, dass nun IRI \(International Resource Identifiers\) und IDN \(Internationalized Domain Names\) bereitgestellt werden.  Aktuelle Benutzer werden keinen Unterschied zum .NET Framework 2.0\-Verhalten feststellen, es sei denn, sie aktivieren die IRI\- und IDN\-Unterstützung explizit.  Damit wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework gewährleistet.  
  
 Zum Aktivieren der Unterstützung für IRI müssen die folgenden zwei Änderungen vorgenommen werden:  
  
1.  Fügen Sie der Datei machine.config im .NET Framework 2.0\-Verzeichnis folgende Zeile hinzu:  
  
    ```  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Geben Sie an, ob IRI\-Analyseregeln angewendet werden sollen.  Dies können Sie in der Datei machine.config oder in der Datei app.config festlegen.  
  
 Durch das Aktivieren von IRI\-Analysen \(iriParsing enabled \= `true`\) werden Normalisierung und Zeichenüberprüfung gemäß den aktuellen IRI\-Regeln in RFC 3987 ausgeführt.  Der Standardwert ist `false`, bei dem Normalisierung und Zeichenüberprüfung gemäß RFC 2396 und RFC 3986 \(für IPv6\-Literale\) ausgeführt werden.  
  
### Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden Codebeispiel wird eine von der <xref:System.Uri>\-Klasse verwendete Konfiguration für die Unterstützung von IRI\-Analyse und IDN\-Namen veranschaulicht.  
  
### Code  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)