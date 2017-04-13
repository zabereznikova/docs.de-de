---
title: "International Resource Identifier-Unterst&#252;tzung in System.Uri | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# International Resource Identifier-Unterst&#252;tzung in System.Uri
Die <xref:System.Uri?displayProperty=fullName>\-Klasse wurde mit Unterstützung des \(International Resource Identifier\) und der IDN \(Internationalized Domain Names\) erweitert.  Diese Erweiterungen sind in .NET Framework 3.5, in 3,0 SP1 und 2,0 SP1 verfügbar.  
  
## IRI\- und IDN\-Unterstützung  
 Webadressen werden in der Regel mithilfe der URI \(Uniform Resource Identifier\) ausgedrückt die einem sehr eingeschränkten Satz aus Zeichen bestehen:  
  
-   ASCII\-Groß\- und Kleinbuchstaben des englischen Alphabets.  
  
-   Ziffern von 0 bis 9.  
  
-   Eine kleine Anzahl anderer ASCII\-Symbole.  
  
 Die Spezifikationen für URIs sind in RFC 2396 und RFC 3986 dokumentiert, die von der IETF \(Internet Engineering Task Force\) veröffentlicht wurden.  
  
 Mit dem stetigen Anwachsen des Internets müssen Ressourcen zunehmend auch in anderen Sprachen als Englisch angegeben werden.  Bezeichner, die dieser Anforderung gerecht werden und Nicht\-ASCII\-Zeichen \(Zeichen im Unicode\/ISO 10646\-Zeichensatz\) zulassen, sind IRIs \(International Resource Identifiers\).  Die Spezifikationen für IRIs sind in RFC 3987 dokumentiert, die von der IETF veröffentlicht wurde.  Wenn IRIs verwendet werden, kann eine URL auch Unicode\-Zeichen enthalten.  
  
 Die vorhandene <xref:System.Uri?displayProperty=fullName>\-Klasse ist erweitert, um IRI\-Unterstützung auf Grundlage RFC 3987 zu unterstützen.  Aktuelle Benutzer werden keinen Unterschied zum .NET Framework 2.0\-Verhalten feststellen, es sei denn, sie aktivieren IRI explizit.  Damit wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework gewährleistet.  
  
 Eine Anwendung kann angeben, ob IDN\-Analysen \(Internationalized Domain Name\) auf Hostnamen angewendet wird und ob IRI\-Analyseregeln beachtet werden sollen.  Dies können Sie in der Datei machine.config oder in der Datei app.config festlegen.  
  
 Durch das Aktivieren von IDN werden alle Unicode\-Bezeichnungen in einem Domänennamen in ihre Punycode\-Entsprechungen konvertiert.  Punycode\-Namen enthalten nur ASCII\-Zeichen und beginnen immer mit dem Präfix xn\-\-.  Der Grund dafür besteht in der Unterstützung vorhandener DNS\-Server im Internet, da die meisten DNS\-Server nur ASCII\-Zeichen unterstützen \(siehe RFC 3940\).  
  
 Das Aktivieren von IRI und IDN wirkt sich auf den Wert der <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>\-Eigenschaft aus.  Das Aktivieren von IRI und IDN kann auch das Verhalten der Methoden <xref:System.Uri.Equals%2A?displayProperty=fullName>, <xref:System.Uri.OriginalString%2A?displayProperty=fullName>, <xref:System.Uri.GetComponents%2A?displayProperty=fullName> und <xref:System.Uri.IsWellFormedOriginalString%2A> ändern.  
  
 Die <xref:System.GenericUriParser?displayProperty=fullName>\-Klasse wurde außerdem so erweitert, dass das Erstellen eines anpassbaren Parsers möglich ist, der IRI und IDN unterstützt.  Das Verhalten eines <xref:System.GenericUriParser?displayProperty=fullName>\-Objekts wird angegeben, indem eine bitweise Kombination der in der <xref:System.GenericUriParserOptions?displayProperty=fullName>\-Enumeration verfügbaren Werte an den <xref:System.GenericUriParser?displayProperty=fullName>\-Konstruktor übergeben wird.  Der <xref:System.GenericUriParserOptions?displayProperty=fullName>\-Typ gibt an, dass der Parser die in RFC 3987 für IRI \(International Resource Identifiers\) angegebenen Analyseregeln unterstützt.  Ob IRI tatsächlich verwendet wird, hängt davon ab, wenn IRI aktiviert ist.  
  
 Der <xref:System.GenericUriParserOptions?displayProperty=fullName>\-Typ gibt an, dass der Parser IDN\-Analysen \(Internationalized Domain Name\) von Hostnamen unterstützt.  Ob IDN tatsächlich verwendet wird, hängt davon ab, wenn IDN aktiviert ist.  
  
 Das Aktivieren von IRI\-Analysen werden Normalisierung und Zeichenüberprüfung gemäß den aktuellen IRI\-Regeln in RFC 3987.  Der Standardwert ist für IRI, das analysiert deaktiviert werden, und sind Normalisierung und Zeichenüberprüfung gemäß RFC 2396 und RFC 3986.  
  
 IRI und IDN konfiguriert, die in der <xref:System.Uri?displayProperty=fullName>\-Klasse verarbeiten, können mit der <xref:System.Configuration.IriParsingElement?displayProperty=fullName> und <xref:System.Configuration.IdnElement?displayProperty=fullName> Konfigurationseinstellungsklassen auch gesteuert werden.  Die Einstellung <xref:System.Configuration.IriParsingElement?displayProperty=fullName> aktiviert oder deaktiviert die IRI\-Verarbeitung in der <xref:System.Uri?displayProperty=fullName>\-Klasse.  Die Einstellung <xref:System.Configuration.IdnElement?displayProperty=fullName> aktiviert oder deaktiviert die IDN\-Verarbeitung in der <xref:System.Uri>\-Klasse.  Mithilfe der Einstellung <xref:System.Configuration.IriParsingElement?displayProperty=fullName> wird IDN auch indirekt gesteuert.  Die IRI\-Verarbeitung muss aktiviert sein, damit IDN\-Verarbeitungsvorgänge ausgeführt werden können.  Wenn die IRI\-Verarbeitung deaktiviert ist, wird die IDN\-Verarbeitung auf die Standardeinstellung festgelegt, in der das .NET Framework 2.0\-Verhalten aus Kompatibilitätsgründen verwendet wird, und es werden keine IDN\-Namen verwendet.  
  
 Die Konfigurationseinstellung für die <xref:System.Configuration.IriParsingElement?displayProperty=fullName> und <xref:System.Configuration.IdnElement?displayProperty=fullName> Konfigurationsklassen wird einmal gelesen, wenn die erste <xref:System.Uri?displayProperty=fullName>\-Klasse erstellt wird.  Änderungen an Konfigurationseinstellungen nach diesem Zeitpunkt werden ignoriert.  
  
## Siehe auch  
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>