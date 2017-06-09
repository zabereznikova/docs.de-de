---
title: "Creating a Cryptographic Scheme | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "encryption [.NET Framework], creating cryptographic schemes"
  - "cryptography [.NET Framework], creating cryptographic schemes"
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating a Cryptographic Scheme
Die kryptografischen Komponenten von .NET Framework können kombiniert werden, um unterschiedliche Schemas zum Ver\- und Entschlüsseln von Daten zu erstellen.  
  
 Für ein einfaches kryptografisches Schema zum Ver\- und Entschlüsseln von Daten können die folgenden Schritte angegeben sein:  
  
1.  Jeder Teilnehmer generiert ein Paar aus privatem und öffentlichem Schlüssel.  
  
2.  Die Teilnehmer tauschen ihre öffentlichen Schlüssel aus.  
  
3.  Jeder Teilnehmer generiert einen geheimen Schlüssel, z. B. für die TripleDES\-Verschlüsselung, und verschlüsselt den neu erstellen Schlüssel mit dem öffentlichen Schlüssel des anderen Teilnehmers.  
  
4.  Jeder Teilnehmer sendet die Daten an den jeweils anderen Teilnehmer und kombiniert den geheimen Schlüssel des anderen in einer bestimmten Folge mit dem eigenen Schlüssel, um einen neuen geheimen Schlüssel zu erstellen.  
  
5.  Danach beginnen die Teilnehmer eine Konversation mit symmetrischer Verschlüsselung.  
  
 Das Erstellen eines kryptografischen Schemas ist keine leichte Aufgabe.  Weitere Informationen zur Verwendung von Kryptografie finden Sie im Thema "Cryptography" in der Platform SDK\-Dokumentation unter "http:\/\/msdn.microsoft.com\/library".  
  
## Siehe auch  
 [Kryptografische Dienste](../../../docs/standard/security/cryptographic-services.md)