---
title: 'Sicherheit in GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Übersicht über die Authentifizierung und Autorisierung von Anrufen und Kanälen in GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503418"
---
# <a name="security-in-grpc-applications"></a>Sicherheit in gRPC-Anwendungen

In jedem realen Szenario ist das Sichern von Anwendungen und Diensten von entscheidender Bedeutung. Sicherheit deckt drei wichtige Bereiche ab: 

* Verschlüsseln von Netzwerk Datenverkehr, um zu verhindern, dass böswillige Hacker Sie abfangen.
* Authentifizieren von Clients und Servern, um Identität und Vertrauensstellung einzurichten.
* Autorisierungs Clients zum Steuern des Zugriffs auf Systeme und Anwenden von Berechtigungen basierend auf der Identität.

> [!NOTE]
> Bei der *Authentifizierung* wird die Identität eines Clients oder Servers festgelegt. Bei der *Autorisierung* wird bestimmt, ob ein Client über die Berechtigung verfügt, auf eine Ressource zuzugreifen oder einen Befehl auszugeben.

In diesem Kapitel werden die Funktionen für die Authentifizierung und Autorisierung in GrpC für ASP.net Core behandelt. Außerdem wird die Netzwerksicherheit über TLS-verschlüsselte Verbindungen erörtert.

## <a name="wcf-authentication-and-authorization"></a>WCF-Authentifizierung und-Autorisierung

In Windows Communication Foundation (WCF) wurden die Authentifizierung und die Autorisierung auf unterschiedliche Weise verarbeitet, je nachdem, welche Transporte und Bindungen verwendet werden. WCF unterstützte verschiedene WS-\*-Sicherheitsstandards. Außerdem wird die Windows-Authentifizierung für HTTP-Dienste unterstützt, die in IIS oder NetTcp-Diensten zwischen Windows-Systemen ausgeführt werden

## <a name="grpc-authentication-and-authorization"></a>GrpC-Authentifizierung und-Autorisierung

die GrpC-Authentifizierung und-Autorisierung funktioniert auf zwei Ebenen:

* Die Authentifizierung/Autorisierung auf aufrufsebene wird in der Regel durch Token verarbeitet, die beim Ausführen des Aufrufens in Metadaten angewendet werden. 
* Bei der Authentifizierung auf Kanal Ebene wird ein Client Zertifikat verwendet, das auf der Verbindungs Ebene angewendet wird. Außerdem können Authentifizierungs-/autorisierungsanmelde-Anmelde Informationen auf Aufrufebene enthalten sein, die automatisch auf jeden Kanal aufgerufen werden. 

Sie können einen oder beide dieser Mechanismen verwenden, um den Dienst zu sichern.

Die ASP.net Core-Implementierung von GrpC unterstützt die Authentifizierung und Autorisierung über die meisten Standard ASP.net Core Mechanismen:

- Rückruf Authentifizierung
  - Azure Active Directory
  - IdentityServer
  - JWT-bearertoken
  - OAuth 2.0
  - OpenID Connect
  - WS-Federation
- Kanal Authentifizierung
  - Clientzertifikat

Die Methoden zum Abrufen von Authentifizierungsmethoden basieren alle auf *Token*. Der einzige wirkliche Unterschied ist die Art und Weise, wie die Token generiert werden, und die Bibliotheken, die zum Überprüfen der Token im ASP.net Core Dienst verwendet werden.

Weitere Informationen finden Sie im Artikel zur [Authentifizierung und Autorisierung](/aspnet/core/grpc/authn-and-authz) .

> [!NOTE]
> Wenn Sie GrpC über eine TLS-verschlüsselte HTTP/2-Verbindung verwenden, wird der gesamte Datenverkehr zwischen Clients und Servern verschlüsselt, auch wenn Sie keine Authentifizierung auf Kanal Ebene verwenden.

In diesem Kapitel wird erläutert, wie Sie Anmelde Informationen und channelanmelde Informationen auf einen GrpC-Dienst anwenden. Außerdem wird gezeigt, wie Anmelde Informationen von einem .net Core-GrpC-Client verwendet werden, um sich beim Dienst zu authentifizieren.

>[!div class="step-by-step"]
>[Zurück](client-libraries.md)
>[Weiter](call-credentials.md)
