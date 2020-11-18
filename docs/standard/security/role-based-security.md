---
title: Rollenbasierte Sicherheit
ms.date: 07/15/2020
helpviewer_keywords:
- role-based security, about role-based security
- user authentication, principals
- principals [.NET]
- security [.NET], role-based
- permissions [.NET], principals
- authentication [.NET], principals
- role-based security, principals
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
ms.openlocfilehash: a03cda3aac06cc247818ccea5c61c673225d7929
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824134"
---
# <a name="role-based-security"></a>Rollenbasierte Sicherheit

Rollen werden häufig in Finanz-oder Geschäftsanwendungen verwendet, um Richtlinien durchzusetzen. Beispielsweise könnte eine Anwendung Beschränkungen der Größe der Transaktion, die verarbeitet wird, abhängig davon erzwingen, ob der anfordernde Benutzer ein Mitglied einer bestimmten Rolle ist. Angestellte können zum Verarbeiten von Transaktionen autorisiert sein, die unter einem bestimmten Schwellenwert liegen, für Abteilungsleiter kann eine höhere Grenze und für Mitglieder der Geschäftsleitung eine noch höhere (oder keine) Grenze angegeben sein. Rollenbasierte Sicherheit kann auch verwendet werden, wenn eine Anwendung mehrere Bestätigungen für das Abschließen einer Aktion benötigt. Ein solcher Fall könnte ein Beschaffungssystem sein, in dem jeder Mitarbeiter eine Bestellanforderung generieren kann, aber nur ein Einkaufssachbearbeiter diese Anforderung in eine Bestellung umwandeln kann, die an einen Lieferanten gesendet werden kann.  
  
 Die rollenbasierte .NET-Sicherheit unterstützt die Autorisierung, indem Informationen über den Prinzipal, der aus einer zugeordneten Identität erstellt wird, für den aktuellen Thread verfügbar gemacht werden. Die Identität (und der Prinzipal, der über sie definiert wird) kann entweder auf einem Windows-Konto basieren oder eine benutzerdefinierte Identität sein, die keinem Windows-Konto zugeordnet ist .NET-Anwendungen können Autorisierungs Entscheidungen auf Grundlage der Identität oder Rollen Mitgliedschaft des Prinzipals oder mit beidem treffen. Eine Rolle ist ein benannter Satz von Prinzipalen, die hinsichtlich der Sicherheit dieselben Berechtigungen haben (z. B. ein Kassierer oder ein Manager). Ein Prinzipal kann einer oder mehrere Rollen angehören. Daher können Anwendungen anhand der Rollenmitgliedschaft bestimmen, ob ein Prinzipal zum Ausführen einer angeforderten Aktion autorisiert ist  
  
 Um eine einfache Verwendung und Konsistenz der Code Zugriffssicherheit zu gewährleisten, stellt die rollenbasierte .NET-Sicherheit <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> Objekte bereit, mit denen die Common Language Runtime Autorisierung auf eine Weise durchführen kann, die Code Zugriffs Sicherheitsüberprüfungen ähnelt. Die <xref:System.Security.Permissions.PrincipalPermission>-Klasse entspricht der Identität oder Rolle, mit der der Prinzipal übereinstimmen muss, und ist sowohl mit deklarativen als auch imperativen Sicherheitsüberprüfungen kompatibel. Sie können in Ihrem Code auch direkt auf Identitätsinformationen eines Prinzipals zugreifen und Rollen- sowie Identitätsprüfungen ausführen.  
  
 .Net bietet rollenbasierte Sicherheitsunterstützung, die flexibel und erweiterbar genug ist, um die Anforderungen eines breiten Spektrums von Anwendungen zu erfüllen. Sie haben die Wahl, auf vorhandene Authentifizierunginfrastrukturen zurückzugreifen, etwa COM+ 1.0 Services, oder ein benutzerdefiniertes Authentifizierungssystem zu erstellen. Rollenbasierte Sicherheit ist besonders gut geeignet für die Verwendung in ASP.NET-Webanwendungen, die hauptsächlich auf dem Server verarbeitet werden. Die rollenbasierte Sicherheit von .net kann jedoch entweder auf dem Client oder auf dem Server verwendet werden.  
  
 Vergewissern Sie sich vor dem Lesen dieses Abschnitts, dass Sie sich mit dem Material vertraut gemacht haben, das in den [wichtigsten Sicherheitskonzepten](key-security-concepts.md)  
  
## <a name="see-also"></a>Siehe auch
  
- [Principal- und Identitätsobjekte](principal-and-identity-objects.md)
- [Schlüsselbegriffe der Sicherheit](key-security-concepts.md)
- <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType>
- [ASP.net Core Sicherheit](/aspnet/core/security/)
