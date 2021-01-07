---
title: 'Verschlüsselung und Netzwerksicherheit: GrpC für WCF-Entwickler'
description: Hinweise zur Netzwerksicherheit und-Verschlüsselung in GrpC
ms.date: 01/06/2021
ms.openlocfilehash: cf4d30ff862e64aadfeacf45ed3768fc14737800
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970140"
---
# <a name="encryption-and-network-security"></a>Verschlüsselung und Netzwerksicherheit

Das Netzwerk Sicherheitsmodell für Windows Communication Foundation (WCF) ist umfangreich und komplex. Er umfasst die Sicherheit auf Transport Ebene mithilfe von HTTPS oder TLS-over-TCP und Sicherheit auf Nachrichten Ebene mithilfe der WS-Security Spezifikation, um einzelne Nachrichten zu verschlüsseln.

GrpC verlässt sicheres Netzwerk auf das zugrunde liegende http/2-Protokoll, das Sie mithilfe von TLS-Zertifikaten sichern können.

Webbrowser sind auf die Verwendung von TLS-Verbindungen für http/2, aber die meisten programmgesteuerten Clients, einschließlich. NET `HttpClient` kann http/2 über unverschlüsselte Verbindungen verwenden.

Für öffentliche APIs sollten Sie immer TLS-Verbindungen verwenden und gültige Zertifikate für ihre Dienste von einer richtigen SSL-Zertifizierungsstelle bereitstellen. [Letsencrypt](https://letsencrypt.org) bietet kostenlose, automatisierte SSL-Zertifikate, und die meisten Hostinginfrastrukturen unterstützen den letsencrypt-Standard mit gängigen Plug-ins oder Erweiterungen.

Für interne Dienste in einem Unternehmensnetzwerk sollten Sie weiterhin TLS verwenden, um den Netzwerk Datenverkehr zu und von ihren GrpC-Diensten zu sichern.

Wenn Sie explizites TLS zwischen Diensten verwenden müssen, die in Kubernetes ausgeführt werden, sollten Sie eine in-Cluster-Zertifizierungsstelle und einen Zertifikat-Manager-Controller wie [Cert-Manager](https://docs.cert-manager.io/en/latest/)verwenden. Anschließend können Sie den Diensten zum Zeitpunkt der Bereitstellung automatisch Zertifikate zuweisen.

>[!div class="step-by-step"]
>[Zurück](channel-credentials.md)
>[Weiter](grpc-in-production.md)
