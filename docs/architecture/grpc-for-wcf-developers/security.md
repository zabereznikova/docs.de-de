---
title: Sicherheit in gRPC-Anwendungen - gRPC für WCF-Entwickler
description: Übersicht über die Anruf- und Kanalauthentifizierung und Autorisierung in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147814"
---
# <a name="security-in-grpc-applications"></a>Sicherheit in gRPC-Anwendungen

In jedem realen Szenario ist die Sicherung von Anwendungen und Diensten unerlässlich. Die Sicherheit umfasst drei Schlüsselbereiche:

* Verschlüsseln des Netzwerkverkehrs, um zu verhindern, dass böswillige Hacker ihn abfangen.
* Authentifizieren von Clients und Servern zum Einrichten von Identität und Vertrauen.
* Autorisiert Clients, den Zugriff auf Systeme zu steuern und Berechtigungen basierend auf der Identität anzuwenden.

> [!NOTE]
> Bei der *Authentifizierung* geht es um das Ermitteln der Identität eines Clients oder Servers. *Bei* der Autorisierung geht es darum, zu ermitteln, ob ein Client über die Berechtigung zum Zugriff auf eine Ressource oder zum Ausgeben eines Befehls verfügt.

In diesem Kapitel werden die Authentifizierungs- und Autorisierungsmöglichkeiten in gRPC für ASP.NET Core behandelt. Außerdem wird die Netzwerksicherheit über TLS-verschlüsselte Verbindungen erörtert.

## <a name="wcf-authentication-and-authorization"></a>WCF-Authentifizierung und -Autorisierung

In Windows Communication Foundation (WCF) wurden Authentifizierung und Autorisierung je nach verwendeten Transporten und Bindungen auf unterschiedliche Weise behandelt. WCF unterstützte verschiedene\* WS-Sicherheitsstandards. Es unterstützte auch die Windows-Authentifizierung für HTTP-Dienste, die in IIS- oder NetTCP-Diensten zwischen Windows-Systemen ausgeführt werden.

## <a name="grpc-authentication-and-authorization"></a>gRPC-Authentifizierung und -Autorisierung

die gRPC-Authentifizierung und -Autorisierung funktioniert auf zwei Ebenen:

* Die Authentifizierung/Autorisierung auf Anrufebene wird in der Regel über Token behandelt, die bei einem Aufruf in Metadaten angewendet werden.
* Die Authentifizierung auf Kanalebene verwendet ein Clientzertifikat, das auf Verbindungsebene angewendet wird. Es kann auch Authentifizierungs-/Autorisierungsanmeldeinformationen auf Aufrufebene enthalten, die auf jeden Aufruf des Kanals automatisch angewendet werden.

Sie können einen oder beide dieser Mechanismen verwenden, um Ihren Dienst zu sichern.

Die ASP.NET Core-Implementierung von gRPC unterstützt die Authentifizierung und Autorisierung über die meisten Standard-ASP.NET Core-Mechanismen:

- Anrufauthentifizierung
  - Azure Active Directory
  - IdentityServer
  - JWT-Trägertoken
  - OAuth 2.0
  - OpenID Connect
  - WS-Federation-
- Kanalauthentifizierung
  - Clientzertifikat

Die *Aufrufauthentifizierungsmethoden*basieren alle auf Token . Der einzige wirkliche Unterschied besteht darin, wie die Token generiert werden und welche Bibliotheken zum Überprüfen der Token im ASP.NET Core-Dienst verwendet werden.

Weitere Informationen finden Sie im [Authentifizierungs- und Autorisierungsartikel.](/aspnet/core/grpc/authn-and-authz)

> [!NOTE]
> Wenn Sie gRPC über eine TLS-verschlüsselte HTTP/2-Verbindung verwenden, wird der gesamte Datenverkehr zwischen Clients und Servern verschlüsselt, auch wenn Sie keine Authentifizierung auf Kanalebene verwenden.

In diesem Kapitel wird gezeigt, wie Anrufanmeldeinformationen und Channel-Anmeldeinformationen auf einen gRPC-Dienst angewendet werden. Außerdem wird gezeigt, wie Anmeldeinformationen von einem .NET Core gRPC-Client verwendet werden, um sich beim Dienst zu authentifizieren.

>[!div class="step-by-step"]
>[VorherigeS](client-libraries.md)
>[Weiter](call-credentials.md)
