---
title: "&lt;servicePointManager&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<servicePointManager>-Element"
  - "servicePointManager-Element"
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;servicePointManager&gt;-Element (Netzwerkeinstellungen)
Konfiguriert Verbindungen zu Netzwerkressourcen.  
  
## Syntax  
  
```  
  
      <servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`checkCertificateName`|Gibt an, ob das System vor dem Verwenden des Zertifikats überprüfen sollte, ob der Name im Zertifikat mit dem Serverhostnamen übereinstimmt.  Der Standardwert ist `true`.|  
|`checkCertificateRevocationList`|Gibt an, ob das System vor dem Verwenden des Zertifikats überprüfen sollte, ob das Zertifikat widerrufen wurde.  Der Standardwert ist `false`.|  
|`dnsRefreshTimeout`|Gibt an, wie lange in Millisekunden Domain Name Service\-\(DNS\-\)Auflösungen in Verbindung mit der DNS Round Robin\-Option zwischengespeichert werden.  Der Standardwert ist 120.000 Millisekunden \(zwei Minuten\).|  
|`enableDnsRoundRobin`|Gibt an, ob DNS\-Auflösungen von Hostnamen mit mehreren IP\-Adressen \(Internet Protocol\) alle Adressen zurückgeben oder nur die erste.  Der Standardwert ist `false`.|  
|`encryptionPolicy`|Gibt die Verschlüsselungsrichtlinie an, die auf eine SSL\/TLS\-Sitzung einer <xref:System.Net.ServicePointManager>\-Instanz angewendet wird.  Die möglichen Werte entsprechen den Werten für die <xref:System.Net.Security.EncryptionPolicy>\-Enumeration.  Die Verwendung von <xref:System.Security.Authentication.CipherAlgorithmType> ist erforderlich, wenn die Verschlüsselungsrichtlinie auf `NoEncryption` festgelegt ist.  Der Standardwert ist `RequireEncryption`.|  
|`expect100Continue`|Gibt an, ob POST\-Methoden erwarten sollten, eine `100-continue`\-Antwort vom Server zu empfangen.  Der Standardwert ist `true`.|  
|`useNagleAlgorithm`|Gibt an ob vom Dienstpunktmanager kontrollierte Verbindungen den Nagle\-Algorithmus verwenden.  Der Standardwert ist `true`.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[Einstellungen](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>\-Namespace.|  
  
## Hinweise  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Siehe auch  
 <xref:System.Net.ServicePointManager>   
 <xref:System.Net.Security.EncryptionPolicy>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)