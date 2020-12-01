---
title: Internetauthentifizierung
description: Hier erfahren Sie mehr über die verschiedenen Clientauthentifizierungsmechanismen, die von System.Net-Klassen für Ihre Anwendungen im .NET Framework unterstützt werden.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [.NET Framework], classes
- IAuthenticationModule interface
- ICredentialLookup interface
- CredentialCache class, about CredentialCache class
- receiving data, authentication
- AuthenticationManager class, about AuthenticationManager class
- Internet, authentication
- sending data, authentication
- network resources, authentication
- user authentication, classes for authentication
- NetworkCredential class, about NetworkCredential class
- client authentication, classes for authentication
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
ms.openlocfilehash: 085ca27dd0cfedc90211b21c10cc8bc5cf1ecd21
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241589"
---
# <a name="internet-authentication"></a>Internetauthentifizierung

Die <xref:System.Net>-Klassen unterstützen eine Vielzahl von Client-Authentifizierungsmechanismen, einschließlich folgender Standardmethoden zur Internetauthentifizierung: Basic, Digest, Negotiate, NTLM, die Kerberos-Authentifizierung und benutzerdefinierte Methoden, die Sie erstellen können.  
  
 Anmeldeinformationen werden in den <xref:System.Net.NetworkCredential>- und <xref:System.Net.CredentialCache>-Klassen gespeichert, die die <xref:System.Net.ICredentials>-Schnittstelle implementieren. Wenn eine dieser Klassen nach Anmeldeinformationen abgefragt wird, gibt sie eine Instanz der Klasse **NetworkCredential** zurück. Der Authentifizierungsvorgang wird durch die <xref:System.Net.AuthenticationManager>-Klasse verwaltet, und der tatsächliche Authentifizierungsprozess wird von einer Authentifizierungsmodulklasse ausgeführt, die die <xref:System.Net.IAuthenticationModule>-Schnittstelle implementiert. Sie müssen ein benutzerdefiniertes Authentifizierungsmodul mit dem **AuthenticationManager** registrieren, bevor dieses verwendet werden kann. Module für Basic-, Digest-, Negotiate-, NTLM- und Kerberos-Authentifizierungsmethoden werden standardmäßig registriert.  
  
 **NetworkCredential** speichert eine Reihe von Anmeldeinformationen durch eine einzelne Internetressource, die von einer URI identifiziert wird. Diese werden als Antwort auf jeden Aufruf der <xref:System.Net.NetworkCredential.GetCredential%2A>-Methode zurückgegeben. Die **NetworkCredential**-Klasse wird üblicherweise von Anwendungen verwendet, die auf eine begrenzte Anzahl von Internetressourcen zugreifen oder von Anwendungen, die in allen Fällen dieselbe Reihe von Anmeldeinformationen verwenden.  
  
 Die **CredentialCache**-Klasse speichert eine Sammlung von Anmeldeinformationen für verschiedene Webressourcen. Wenn die <xref:System.Net.CredentialCache.GetCredential%2A>-Methode aufgerufen wird, gibt **CredentialCache** die richtige Reihe von Anmeldeinformationen zurück. Dies wird durch die URI der Webressource und das angeforderte Authentifizierungsschema bestimmt. Anwendungen, die eine Vielzahl von Internetressourcen mit verschiedenen Authentifizierungsschemas verwenden, profitieren von der Anwendung der **CredentialCache**-Klasse, da diese alle Anmeldeinformationen speichert und auf Anforderung bereitstellt.  
  
 Wenn eine Internetressource die Authentifizierung anfordert, sendet die <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>-Methode den <xref:System.Net.WebRequest> zusammen mit der Anforderung für Anmeldeinformationen an den **AuthenticationManager**. Die Anforderung wird dann gemäß dem folgenden Prozess authentifiziert:  
  
1. Der **AuthenticationManager** ruft die <xref:System.Net.IAuthenticationModule.Authenticate%2A>-Methode auf jedem der registrierten Authentifizierungsmodule in der Reihenfolge auf, in der sie registriert wurden. Der **AuthenticationManager** verwendet das erste Modul, das nicht **NULL** zurückgibt, um den Authentifizierungsprozess durchzuführen. Die Einzelheiten des Prozesses unterscheiden sich je nach Typ der beteiligten Authentifizierungsmodule.  
  
2. Wenn der Authentifizierungsprozess abgeschlossen ist, gibt das Authentifizierungsmodul <xref:System.Net.Authorization> an **WebRequest** zurück, das die Informationen enthält, die für den Zugriff auf die Internetressource benötigt werden.  
  
 Einige Authentifizierungsschemas können einen Benutzer authentifizieren, ohne zuvor eine Anforderung für eine Ressource durchzuführen. Eine Anwendung kann Zeit sparen, indem der Benutzer mit der Ressource präauthentifiziert wird. So wird mindestens ein Roundtrip zum Server vermieden. Sie können die Authentifizierung auch während des Programmstarts durchführen, um später besser auf den Benutzer reagieren zu können. Authentifizierungsschemas, die die Präauthentifizierung verwenden können, legen die <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A>-Eigenschaft auf **TRUE** fest.  
  
## <a name="see-also"></a>Siehe auch

- [Standard- und Digestauthentifizierung](basic-and-digest-authentication.md)
- [NTLM- und Kerberos-Authentifizierung](ntlm-and-kerberos-authentication.md)
- [Security in Network Programming (Sicherheit in der Netzwerkprogrammierung)](security-in-network-programming.md)
