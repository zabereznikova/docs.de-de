---
title: 'Verschlüsselung und Netzwerksicherheit: GrpC für WCF-Entwickler'
description: Hinweise zur Netzwerksicherheit und-Verschlüsselung in GrpC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 67ee1ffaf00ea0cc6b771ede9f49b6a691af0968
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841618"
---
# <a name="encryption-and-network-security"></a>Verschlüsselung und Netzwerksicherheit

Das Netzwerk Sicherheitsmodell von WCF ist umfangreich und komplex, einschließlich Sicherheit auf Transport Ebene mithilfe von HTTPS oder TLS-over-TCP und Sicherheit auf Nachrichten Ebene mithilfe der WS-Security-Spezifikation zum Verschlüsseln einzelner Nachrichten.

GrpC verlässt sicheres Netzwerk auf das zugrunde liegende http/2-Protokoll, das mithilfe regulärer TLS-Zertifikate geschützt werden kann.

Webbrowser sind auf die Verwendung von TLS-Verbindungen für http/2, aber die meisten programmgesteuerten Clients, einschließlich. NET-`HttpClient`, kann http/2 über unverschlüsselte Verbindungen verwenden. `HttpClient` *erfordert* standardmäßig eine Verschlüsselung, aber Sie können dies mithilfe eines <xref:System.AppContext> Schalters außer Kraft setzen.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Für öffentliche APIs sollten Sie immer TLS-Verbindungen verwenden und gültige Zertifikate für ihre Dienste von einer richtigen SSL-Zertifizierungsstelle bereitstellen. [Letsencrypt](https://letsencrypt.org) bietet kostenlose, automatisierte SSL-Zertifikate, und die meisten Hostinginfrastrukturen unterstützen den letsencrypt-Standard mit gängigen Plug-ins oder Erweiterungen.

Für interne Dienste in einem Unternehmensnetzwerk sollten Sie weiterhin TLS verwenden, um den Netzwerk Datenverkehr zu und von ihren GrpC-Diensten zu sichern.

Die Kommunikation zwischen den-Diensten in einem Cluster wie Kubernetes oder docker Swarm wird im allgemeinen automatisch von der Netzwerkebene des Containers verschlüsselt, sodass die Implementierung von TLS in Diensten, die ausschließlich in einem solchen Cluster ausgeführt werden, nicht erforderlich ist. Weitere Informationen zu diesem Thema finden Sie im Abschnitt "Service Mesh" des nächsten Kapitels.

Wenn Sie explizites TLS zwischen Diensten verwenden müssen, die in Kubernetes ausgeführt werden, sollten Sie die Verwendung einer in-Cluster-Zertifizierungsstelle und eines Zertifikat-Manager-Controllers wie [Cert-Manager](https://docs.cert-manager.io/en/latest/) in Erwägung gezogen werden, um Dienste zum Zeitpunkt der Bereitstellung automatisch

>[!div class="step-by-step"]
>[Zurück](channel-credentials.md)
>[Weiter](grpc-in-production.md)
