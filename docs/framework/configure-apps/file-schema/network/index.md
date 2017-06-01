---
title: "Netzwerkeinstellungsschema | Microsoft Docs"
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
helpviewer_keywords: 
  - "Konfigurationseinstellungen [.NET Framework], Netzwerke"
  - "Verbindungen [.NET Framework], Netzwerkkonfigurationselemente"
  - "Elemente [.NET Framework], Netzwerkkonfigurationselemente"
  - "Internet, Netzwerkkonfigurationselemente"
  - "Netzwerkkonfigurationselemente"
  - "Netzwerkressourcen, Netzwerkkonfigurationselemente"
  - "Netzwerkeinstellungen"
  - "Empfangen von Daten, Netzwerkkonfigurationselemente"
  - "Senden von Daten, Netzwerkkonfigurationselemente"
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Netzwerkeinstellungsschema
Netzwerkeinstellungen geben an, wie .NET Framework und dem Internet hergestellt werden.  In der folgenden Tabelle ist die Funktion der einzelnen untergeordneten Konfigurationselemente unter [\<system.Net\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) beschrieben.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<authenticationModules\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Gibt die zum Authentifizieren von Internetanforderungen verwendeten Module an.|  
|[\<connectionManagement\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl der Verbindungen zu Internethosts an.|  
|[\<defaultProxy\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Gibt den für HTTP\-Anforderungen an das Internet verwendeten Proxyserver an.|  
|[\<mailSettings\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Enthält Einstellungen für E\-Mail\-Sendeoptionen.|  
|[\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Gibt die zum Anfordern von Informationen von Internethosts verwendeten Module an.|  
|[\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=fullName>\-Namespace.|  
|[\<webRequestModules\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die zum Anfordern von Informationen von Internethosts verwendeten Module an.|  
  
 URIeinstellungen geben an, wie .NET Framework durch Webadressen behandelt, die mit der URL \(Uniform Resource Identifier \(URIs\) ausgedrückt werden.  In der folgenden Tabelle ist die Funktion der einzelnen untergeordneten Konfigurationselemente unter [\<Uri\>\-Element \(Uri\-Einstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md) beschrieben.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<idn\>\-Element \(Uri\-Einstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Gibt an, ob IDN\-Analysen \(Internationalized Domain Name\) auf Hostnamen angewendet werden.|  
|[\<iriParsing\>\-Element \(Uri\-Einstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Gibt an, ob IRI\-Analysen \(International Resource Identifier\) auf einen <xref:System.Uri> angewendet werden sollen und ob IRI\-Analyseregeln beachtet werden sollen.|  
|[\<schemeSettings\>\-Element \(Uri\-Einstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Gibt an, wie ein <xref:System.Uri>\-Objekt für bestimmte Schemen analysiert wird.|  
  
## Siehe auch  
 [Konfigurieren von Internetanwendungen](../../../../../docs/framework/network-programming/configuring-internet-applications.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)