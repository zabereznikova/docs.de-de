---
title: 'Sicherheit in GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Übersicht über die Authentifizierung und Autorisierung von Anrufen und Kanälen in GrpC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d0b7ff5bef755c5eeb9b3c419dcda1cb75ac4031
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841372"
---
# <a name="security-in-grpc-applications"></a>Sicherheit in gRPC-Anwendungen

In jedem realen Szenario ist das Sichern von Anwendungen und Diensten von entscheidender Bedeutung. Die Sicherheit deckt drei wichtige Bereiche ab: das Verschlüsseln von Netzwerk Datenverkehr, um zu verhindern, dass Sie von böswilligen Actors abgefangen werden. Authentifizieren von Clients und Servern zum Einrichten von Identität und Vertrauensstellung und autorisierender Clients zum Steuern des Zugriffs auf Systeme und Anwenden von Berechtigungen basierend auf der Identität.

> [!NOTE]
> Bei der **Authentifizierung** wird die Identität eines Clients oder Servers festgelegt. Bei der **Autorisierung** wird bestimmt, ob ein Client über die Berechtigung verfügt, auf eine Ressource zuzugreifen oder einen Befehl auszugeben.

In diesem Kapitel werden die Funktionen für die Authentifizierung und Autorisierung in GrpC für ASP.net Core behandelt und die Netzwerksicherheit mithilfe von TLS-verschlüsselten Verbindungen erörtert.

## <a name="wcf-authentication-and-authorization"></a>WCF-Authentifizierung und-Autorisierung

In WCF wurden Authentifizierung und Autorisierung je nach verwendeter Transporte und Bindungen auf unterschiedliche Weise gehandhabt. WCF unterstützte verschiedene WS-\*-Sicherheitsstandards sowie die Windows-Authentifizierung für HTTP-Dienste, die in IIS oder NetTcp-Diensten zwischen Windows-Systemen ausgeführt werden.

## <a name="grpc-authentication-and-authorization"></a>GrpC-Authentifizierung und-Autorisierung

die GrpC-Authentifizierung und-Autorisierung funktioniert auf zwei Ebenen. Die Authentifizierung/Autorisierung auf aufrufsebene wird in der Regel mithilfe von Token gehandhabt, die bei der Anforderung in Metadaten angewendet werden. Bei der Authentifizierung auf Kanal Ebene wird ein Client Zertifikat verwendet, das auf der Verbindungs Ebene angewendet wird. Außerdem können Authentifizierungs-/autorisierungsanmelde-Anmelde Informationen auf Aufrufebene enthalten sein, die automatisch auf jeden Kanal aufgerufen werden. Sie können einen oder beide dieser Mechanismen verwenden, um den Dienst zu sichern.

Die ASP.net Core-Implementierung von GrpC unterstützt die Authentifizierung und Autorisierung unter Verwendung der meisten Standard ASP.net Core Mechanismen:

- Rückruf Authentifizierung
  - Azure Active Directory
  - IdentityServer
  - JWT-bearertoken
  - OAuth 2,0
  - OpenID Connect
  - WS-Federation
- Kanal Authentifizierung
  - Clientzertifikat

Die Methoden zum Abrufen von Authentifizierungsmethoden basieren alle auf *Token*. Der einzige wirkliche Unterschied ist die Art und Weise, wie das Token generiert wird, und die Bibliotheken, die zum Überprüfen der Token im ASP.net Core Dienst verwendet werden.

Weitere Informationen finden Sie in der [Dokumentation zur Authentifizierung und Autorisierung auf Microsoft-Dokumentation](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).

> [!NOTE]
> Wenn Sie GrpC über eine TLS-verschlüsselte HTTP/2-Verbindung verwenden, wird der gesamte Datenverkehr zwischen Clients und Servern verschlüsselt, auch wenn Sie keine Authentifizierung auf Kanal Ebene verwenden.

In diesem Kapitel wird erläutert, wie Sie Anmelde Informationen und channelanmelde Informationen für einen GrpC-Dienst anwenden und wie Sie Anmelde Informationen von einem .net Core-GrpC-Client verwenden, um sich beim Dienst zu authentifizieren.

>[!div class="step-by-step"]
>[Zurück](client-libraries.md)
>[Weiter](call-credentials.md)
