---
title: "Internetauthentifizierung | Microsoft Docs"
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
helpviewer_keywords: 
  - "Authentifizierung [.NET Framework], Klassen"
  - "IAuthenticationModule-Schnittstelle"
  - "ICredentialLookup-Schnittstelle"
  - "CredentialCache-Klasse, Informationen zur CredentialCache-Klasse"
  - "Empfangen von Daten, Authentifizierung"
  - "AuthenticationManager-Klasse, Informationen zur AuthenticationManager-Klasse"
  - "Internet, Authentifizierung"
  - "Senden von Daten, Authentifizierung"
  - "Netzwerkressourcen, Authentifizierung"
  - "Benutzerauthentifizierung, Klassen für die Authentifizierung"
  - "NetworkCredential-Klasse, Informationen zur NetworkCredential-Klasse"
  - "Clientauthentifizierung, Klassen für die Authentifizierung"
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Internetauthentifizierung
Die <xref:System.Net>\-Klassen unterstützen eine Vielzahl von Clientauthentifizierungsmechanismen, einschließlich der grundlegenden Standardinternet\-Authentifizierungsmethoden, Digest\-, angewendet werden, NTLM und Kerberos\-Authentifizierung sowie benutzerdefinierte Methoden aus, die Sie erstellen können.  
  
 Authentifizierungsinformationen werden in den <xref:System.Net.NetworkCredential> und <xref:System.Net.CredentialCache>\-Klassen gespeichert, die die <xref:System.Net.ICredentials>\-Schnittstelle implementieren.  Wenn eine dieser Klassen für Anmeldeinformationen abgefragt wird, wird eine Instanz der **NetworkCredential**\-Klasse zurück.  Der Authentifizierungsprozess wird durch die <xref:System.Net.AuthenticationManager>\-Klasse verwaltet, und der tatsächliche Authentifizierungsprozess wird durch eine Authentifizierungsmodulklasse ausgeführt, die die <xref:System.Net.IAuthenticationModule>\-Schnittstelle implementiert.  Sie müssen ein benutzerdefiniertes Authentifizierungsmodul mit **AuthenticationManager** registrieren, bevor es verwendet werden kann, Module für das grundlegende, Digest\-, angewendet werden, NTLM aus, und Kerberos\-Authentifizierungsmethoden werden standardmäßig registriert.  
  
 **NetworkCredential** speichert einen Satz von Anmeldeinformationen, die mit einer einzelnen Internetressource zugeordnet werden, die durch einen URI angegeben wird und sie als Reaktion auf einen beliebigen Aufruf der <xref:System.Net.NetworkCredential.GetCredential%2A>\-Methode zurück.  Die **NetworkCredential**\-Klasse wird normalerweise von Anwendungen verwendet, die eine begrenzte Anzahl für Internetressourcen oder von Anwendungen zugreifen, die den gleichen Satz von Anmeldeinformationen in allen Fällen verwenden.  
  
 Die **CredentialCache**\-Klasse speichert eine Auflistung Anmeldeinformationen für verschiedene Webressourcen.  Wenn die <xref:System.Net.CredentialCache.GetCredential%2A>\-Methode aufgerufen wird, gibt **CredentialCache** den richtigen Satz von Anmeldeinformationen zurück, wie durch den URI der Webressource und des angeforderten Authentifizierungsschemas bestimmt.  Anwendungen, die eine Vielzahl von Internetressourcen mit verschiedenen Authentifizierungsschemas profitieren von der Anwendung der **CredentialCache**\-Klasse verwenden, da sie alle Anmeldeinformationen speichert und stellt sie bereit, wie angefordert.  
  
 Wenn eine Internetressource Authentifizierung erfordert, sendet die Methode <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=fullName><xref:System.Net.WebRequest> zu **AuthenticationManager** zusammen mit dem Anforderungen für Anmeldeinformationen.  Die Anforderung wird dann entsprechend dem folgenden Prozess authentifiziert:  
  
1.  **AuthenticationManager** ruft die <xref:System.Net.IAuthenticationModule.Authenticate%2A>\-Methode auf jedem der registrierten Authentifizierungsmodule in der Reihenfolge auf, die sie registriert wurden.  **AuthenticationManager** verwendet das erste Modul, das nicht **NULL** zurückgibt, um den Authentifizierungsprozess durchzuführen.  Die Details des Prozesses variieren je nach Art des Authentifizierungsmoduls beziehen.  
  
2.  Wenn der Authentifizierungsprozess abgeschlossen ist, gibt das Authentifizierungsmodul <xref:System.Net.Authorization> zu **WebRequest** zurück, das die Informationen enthält, die erforderlich sind, um auf die Internetressource zuzugreifen.  
  
 Einige Authentifizierungsschemas können einen Benutzer authentifizieren, ohne eine Anforderung für eine Ressource zunächst zu stellen.  Eine Anwendung kann Zeit sparen, indem sie den Benutzer der Ressource preauthenticating und so mindestens einen Roundtrip zum Server entfernt.  Oder, sie kann Authentifizierung während des Programmstarts später ausführen, um dem Benutzer schneller sein.  Authentifizierungsschemas bereit, die preauthentication verwenden können, legen Sie die [CanPreAuthenticate](frlrfsystemnetiauthenticationmoduleclasspreauthenticatetopic)\-Eigenschaft auf **true** fest.  
  
## Siehe auch  
 [Standard\- und Digestauthentifizierung](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [NTLM\- und Kerberos\-Authentifizierung](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Sicherheit in der Netzwerkprogrammierung](../../../docs/framework/network-programming/security-in-network-programming.md)