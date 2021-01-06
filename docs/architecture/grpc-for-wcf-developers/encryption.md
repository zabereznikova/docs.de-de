---
title: 'Verschlüsselung und Netzwerksicherheit: GrpC für WCF-Entwickler'
description: Hinweise zur Netzwerksicherheit und-Verschlüsselung in GrpC
ms.date: 12/15/2020
ms.openlocfilehash: 0735158ed69ce425c4f00eed6c42689b888a1885
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938623"
---
# <a name="encryption-and-network-security"></a>Verschlüsselung und Netzwerksicherheit

Das Netzwerk Sicherheitsmodell für Windows Communication Foundation (WCF) ist umfangreich und komplex. Er umfasst die Sicherheit auf Transport Ebene mithilfe von HTTPS oder TLS-over-TCP und Sicherheit auf Nachrichten Ebene mithilfe der WS-Security Spezifikation, um einzelne Nachrichten zu verschlüsseln.

GrpC verlässt sicheres Netzwerk auf das zugrunde liegende http/2-Protokoll, das Sie mithilfe von TLS-Zertifikaten sichern können.

Webbrowser sind auf die Verwendung von TLS-Verbindungen für http/2, aber die meisten programmgesteuerten Clients, einschließlich. NET `HttpClient` kann http/2 über unverschlüsselte Verbindungen verwenden. `HttpClient` erfordert standardmäßig Verschlüsselung, aber Sie können dieses Verhalten mithilfe eines-Schalters außer Kraft setzen <xref:System.AppContext> .

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Für öffentliche APIs sollten Sie immer TLS-Verbindungen verwenden und gültige Zertifikate für ihre Dienste von einer richtigen SSL-Zertifizierungsstelle bereitstellen. [Letsencrypt](https://letsencrypt.org) bietet kostenlose, automatisierte SSL-Zertifikate, und die meisten Hostinginfrastrukturen unterstützen den letsencrypt-Standard mit gängigen Plug-ins oder Erweiterungen.

Für interne Dienste in einem Unternehmensnetzwerk sollten Sie weiterhin TLS verwenden, um den Netzwerk Datenverkehr zu und von ihren GrpC-Diensten zu sichern.

Wenn Sie explizites TLS zwischen Diensten verwenden müssen, die in Kubernetes ausgeführt werden, sollten Sie eine in-Cluster-Zertifizierungsstelle und einen Zertifikat-Manager-Controller wie [Cert-Manager](https://docs.cert-manager.io/en/latest/)verwenden. Anschließend können Sie den Diensten zum Zeitpunkt der Bereitstellung automatisch Zertifikate zuweisen.

>[!div class="step-by-step"]
>[Zurück](channel-credentials.md)
>[Weiter](grpc-in-production.md)
