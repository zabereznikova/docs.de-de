---
title: "&lt;Uri&gt;-Element (Uri-Einstellungen) | Microsoft Docs"
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
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;Uri&gt;-Element (Uri-Einstellungen)
Enthält Einstellungen, die angeben, wie .NET Framework durch URIs \(Uniform Resource Identifier\) ausgedrückte Webadressen behandelt.  
  
## Schemahierarchie  
 [\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<uri\>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## Syntax  
  
```  
<uri>  
</uri>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[idn](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Gibt an, ob IDN\-Analysen \(Internationalized Domain Name\) auf Hostnamen angewendet werden.|  
|[IriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Gibt an, ob IRI\-Analysen \(International Resource Identifier\) auf einen <xref:System.Uri> angewendet werden sollen und ob IRI\-Analyseregeln beachtet werden sollen.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Gibt an, wie ein <xref:System.Uri>\-Objekt für bestimmte Schemen analysiert wird.|  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[übernehmen](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Enthält Einstellungen für alle Namespaces.|  
  
## Hinweise  
 Das `uri`\-Element enthält Einstellungen für Member der <xref:System.Uri>\-Klasse, die von Klassen im <xref:System.Net>\-Namespace verwendet werden.  Mit diesen Einstellungen wird die Unterstützung für IRI und IDN konfiguriert.  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden Codebeispiel wird eine von der <xref:System.Uri>\-Klasse verwendete Konfiguration für die Unterstützung von IRI\-Analyse und IDN\-Namen veranschaulicht.  Im Beispiel werden ebenfalls alle Schemaeinstellungen gelöscht, und anschließend wird Unterstützung für das Nichthinzufügen von Escapezeichen zu als Prozentwert codierten Pfadabgrenzungszeichen für das HTTP\-Schema hinzugefügt.  
  
### Code  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## Siehe auch  
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)