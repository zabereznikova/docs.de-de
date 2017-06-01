---
title: "Schema f&#252;r Kryptografieeinstellungen | Microsoft Docs"
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
  - "Konfigurationsschema [.NET Framework], Kryptografie"
  - "Konfigurationsabschnitte [.NET Framework]"
  - "Konfigurationseinstellungen [.NET Framework], Kryptografie"
  - "Kryptografie, Zuordnen von Algorithmennamen"
  - "Kryptografie, Einstellungsschema"
  - "Elemente [.NET Framework], Kryptografie"
  - "Schemakonfigurationseinstellungen"
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Schema f&#252;r Kryptografieeinstellungen
Die im Schema für Kryptografieeinstellungen enthaltenen Elemente geben an, wie angezeigte Algorithmusnamen Klassen zugeordnet werden, in denen Kryptografiealgorithmen implementiert werden.  
  
 [\<konfiguration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<mscorlib\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [\<CryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [\<cryptoClasses\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<cryptoClasses\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|Enthält eine Liste von kryptografischen Klassen, die eine Zuordnung in einen Anzeigenamen im **\<nameEntry\>**\-Element verfügen.|  
|[\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Enthält eine mehr, die eine Zuordnung in einen Anzeigenamen im **\<nameEntry\>**\-Element verfügt.|  
|[\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|Enthält Kryptografieeinstellungen.|  
|[\<CryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Enthält Zuordnungen von Klassen zu angezeigten Namen.|  
|[\<mscorlibelement\>für Kryptographieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|Enthält das **\<cryptographySettings\>**\-Element.|  
|[\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|Ordnet einen Klassennamen einem angezeigten Algorithmusnamen zu, wodurch eine Klasse viele angezeigte Namen aufweisen kann.|  
|[\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Ordnet einen ASN.1‑Objektbezeichner \(OID\) einem angezeigten Namen zu.|  
|[\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Enthält ASN.1‑OID\-Zuordnungen zu Klassen.|  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)