---
title: 'Verschlüsselung und Netzwerksicherheit: GrpC für WCF-Entwickler'
description: Hinweise zur Netzwerksicherheit und-Verschlüsselung in GrpC
ms.date: 09/02/2019
ms.openlocfilehash: f8a7aeaf2a65e4ff56ac33d728e40f09a436f7a6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542767"
---
# <a name="encryption-and-network-security"></a>Verschlüsselung und Netzwerksicherheit

Das Netzwerk Sicherheitsmodell für Windows Communication Foundation (WCF) ist umfangreich und komplex. Sie beinhaltet Sicherheit auf Transport Ebene mithilfe von HTTPS oder TLS-over-TCP und Sicherheit auf Nachrichten Ebene, indem die WS-Security-Spezifikation zum Verschlüsseln einzelner Nachrichten verwendet wird.

GrpC verlässt sicheres Netzwerk auf das zugrunde liegende http/2-Protokoll, das Sie mithilfe von TLS-Zertifikaten sichern können.

Webbrowser sind auf die Verwendung von TLS-Verbindungen für http/2, aber die meisten programmgesteuerten Clients, einschließlich. NET-`HttpClient`, kann http/2 über unverschlüsselte Verbindungen verwenden. `HttpClient` erfordert standardmäßig eine Verschlüsselung, Sie können diese jedoch überschreiben, indem Sie einen <xref:System.AppContext>-Schalter verwenden.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Für öffentliche APIs sollten Sie immer TLS-Verbindungen verwenden und gültige Zertifikate für ihre Dienste von einer richtigen SSL-Zertifizierungsstelle bereitstellen. [Letsencrypt](https://letsencrypt.org) bietet kostenlose, automatisierte SSL-Zertifikate, und die meisten Hostinginfrastrukturen unterstützen den letsencrypt-Standard mit gängigen Plug-ins oder Erweiterungen.

Für interne Dienste in einem Unternehmensnetzwerk sollten Sie weiterhin TLS verwenden, um den Netzwerk Datenverkehr zu und von ihren GrpC-Diensten zu sichern.

Wenn Sie explizites TLS zwischen Diensten verwenden müssen, die in Kubernetes ausgeführt werden, sollten Sie eine in-Cluster-Zertifizierungsstelle und einen Zertifikat-Manager-Controller wie [Cert-Manager](https://docs.cert-manager.io/en/latest/)verwenden. Anschließend können Sie den Diensten zum Zeitpunkt der Bereitstellung automatisch Zertifikate zuweisen.

>[!div class="step-by-step"]
>[Zurück](channel-credentials.md)
>[Weiter](grpc-in-production.md)
