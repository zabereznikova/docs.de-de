---
title: "&lt;idn&gt;-Element (Uri-Einstellungen) | Microsoft Docs"
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
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;idn&gt;-Element (Uri-Einstellungen)
Gibt an, ob IDN\-Analysen \(Internationalized Domain Name\) auf Hostnamen angewendet werden.  
  
## Schemahierarchie  
 [\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri\>\-Element \(Uri\-Einstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn\>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## Syntax  
  
```  
<idn  
  enabled="All|AllExceptIntranet|None"  
/idn>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|`enabled`|Gibt an, ob IDN\-Analysen \(Internationalized Domain Name\) auf Hostnamen angewendet werden. Der Standardwert ist Keine.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie .NET Framework durch URIs \(Uniform Resource Identifier\) ausgedrückte Webadressen behandelt.|  
  
## Hinweise  
 Die vorhandene <xref:System.Uri>\-Klasse wurde in .NET Framework 3.5, 3.0 SP1 und 2.0 SP1 so erweitert, dass nun IRI \(International Resource Identifiers\) und IDN \(Internationalized Domain Names\) unterstützt werden.  Aktuelle Benutzer werden keinen Unterschied zum .NET Framework 2.0\-Verhalten feststellen, es sei denn, sie aktivieren die IRI\- und IDN\-Unterstützung explizit.  Damit wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework gewährleistet.  
  
 Zum Aktivieren der Unterstützung für IRI müssen die folgenden zwei Änderungen vorgenommen werden:  
  
1.  Fügen Sie der Datei machine.config im .NET Framework 2.0\-Verzeichnis folgende Zeile hinzu:  
  
    ```  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Geben Sie an, ob IDN\-Analysen \(Internationalized Domain Name\) auf den Domänennamen angewendet und ob IRI\-Analyseregeln beachtet werden sollen.  Dies können Sie in der Datei machine.config oder in der Datei app.config festlegen.  
  
 In Abhängigkeit von den verwendeten DNS\-Servern gibt es drei mögliche Werte für IDN:  
  
-   idn enabled \= All  
  
     Durch diesen Wert werden alle Unicode\-Domänennamen in ihre Punycode\-Entsprechungen \(IDN\-Namen\) konvertiert.  
  
-   idn enabled \= AllExceptIntranet  
  
     Durch diesen Wert werden alle Unicode\-Domänennamen außerhalb des lokalen Intranets so konvertiert, dass die Punycode\-Entsprechungen \(IDN\-Namen\) verwendet werden.  Wenn internationale Namen im lokalen Intranet verarbeitet werden sollen, müssen die DNS\-Server im Intranet die Auflösung von Unicode\-Namen unterstützen.  
  
-   idn enabled \= None  
  
     Durch diesen Wert werden keine Unicode\-Domänennamen in ihre Punycode\-Entsprechungen konvertiert.  Dies ist der Standardwert, der dem .NET Framework 2.0\-Verhalten entspricht.  
  
 Durch das Aktivieren von IDN werden alle Unicode\-Bezeichnungen in einem Domänennamen in ihre Punycode\-Entsprechungen konvertiert.  Punycode\-Namen enthalten nur ASCII\-Zeichen und beginnen immer mit dem Präfix xn\-\-.  Der Grund dafür besteht in der Unterstützung vorhandener DNS\-Server im Internet, da die meisten DNS\-Server nur ASCII\-Zeichen unterstützen \(siehe RFC 3940\).  
  
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
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)