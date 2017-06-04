---
title: "Role-Based Security | Microsoft Docs"
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
  - "role-based security, about role-based security"
  - "user authentication, principals"
  - "principals [.NET Framework]"
  - "security [.NET Framework], role-based"
  - "permissions [.NET Framework], principals"
  - "authentication [.NET Framework], principals"
  - "role-based security, principals"
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Role-Based Security
Rollen werden häufig in Finanz\-oder Geschäftsanwendungen verwendet, um Richtlinien durchzusetzen.  Beispielsweise könnte eine Anwendung Beschränkungen der Größe der Transaktion, die verarbeitet wird, abhängig davon erzwingen, ob der anfordernde Benutzer ein Mitglied einer bestimmten Rolle ist.  Angestellte können zum Verarbeiten von Transaktionen autorisiert sein, die unter einem bestimmten Schwellenwert liegen, für Abteilungsleiter kann eine höhere Grenze und für Mitglieder der Geschäftsleitung eine noch höhere \(oder keine\) Grenze angegeben sein.  Rollenbasierte Sicherheit kann auch verwendet werden, wenn eine Anwendung mehrere Bestätigungen für das Abschließen einer Aktion benötigt.  Ein solcher Fall könnte ein Beschaffungssystem sein, in dem jeder Mitarbeiter eine Bestellanforderung generieren kann, aber nur ein Einkaufssachbearbeiter diese Anforderung in eine Bestellung umwandeln kann, die an einen Lieferanten gesendet werden kann.  
  
 Die rollenbasierte Sicherheit von .NET Framework unterstützt Autorisierung, indem sie dem aktuellen Thread Informationen über den Prinzipal verfügbar macht, der aus einer zugehörigen Identität erstellt wird.  Die Identität \(und der Prinzipal, der über sie definiert wird\) kann entweder auf einem Windows\-Konto basieren oder eine benutzerdefinierte Identität sein, die keinem Windows\-Konto zugeordnet ist  .NET Framework\-Anwendungen können für das Treffen von Autorisierungsentscheidungen die Identität oder die Rollenmitgliedschaft des Prinzipals oder beides verwenden.  Eine Rolle ist ein benannter Satz von Prinzipalen, die hinsichtlich der Sicherheit dieselben Berechtigungen haben \(z. B. ein Kassierer oder ein Manager\).  Ein Prinzipal kann einer oder mehrere Rollen angehören.  Daher können Anwendungen anhand der Rollenmitgliedschaft bestimmen, ob ein Prinzipal zum Ausführen einer angeforderten Aktion autorisiert ist  
  
 Damit Benutzerfreundlichkeit und Konsistenz mit der Codezugriffssicherheit gegeben sind, stellt die rollenbasierte Sicherheit von .NET Framework <xref:System.Security.Permissions.PrincipalPermission?displayProperty=fullName>\-Objekte bereit, die es der Common Language Runtime ermöglichen, Autorisierung auf eine Weise vorzunehmen, die Prüfungen der Codezugriffssicherheit ähnlich ist.  Die <xref:System.Security.Permissions.PrincipalPermission>\-Klasse entspricht der Identität oder Rolle, mit der der Prinzipal übereinstimmen muss, und ist sowohl mit deklarativen als auch imperativen Sicherheitsüberprüfungen kompatibel.  Sie können in Ihrem Code auch direkt auf Identitätsinformationen eines Prinzipals zugreifen und Rollen\- sowie Identitätsprüfungen ausführen.  
  
 .NET Framework bietet Unterstützung für rollenbasierte Sicherheit, die genügend flexibel und erweiterbar ist, um die Anforderungen einer großen Bandbreite von Anwendungen zu erfüllen.  Sie haben die Wahl, auf vorhandene Authentifizierunginfrastrukturen zurückzugreifen, etwa COM\+ 1.0 Services, oder ein benutzerdefiniertes Authentifizierungssystem zu erstellen.  Rollenbasierte Sicherheit ist besonders gut geeignet für die Verwendung in ASP.NET\-Webanwendungen, die hauptsächlich auf dem Server verarbeitet werden.  Die rollenbasierte Sicherheit von .NET Framework kann aber sowohl auf dem Client als auch auf dem Server verwendet werden.  
  
 Vor dem Lesen dieses Abschnitts sollten Sie sich mit den Informationen vertraut machen, die in [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md) zu finden sind.  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md)|Erläutert das Einrichten und Verwalten von Windows\- und generischen Identitäten und Prinzipalen.|  
|[Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)|Stellt die grundlegenden Konzepte vor, die Sie verstehen müssen, bevor Sie .NET Framework\-Sicherheit verwenden.|  
  
## Verweis  
 <xref:System.Security.Permissions.PrincipalPermission?displayProperty=fullName>