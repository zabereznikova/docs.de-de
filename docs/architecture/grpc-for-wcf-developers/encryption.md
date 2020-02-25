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
# <a name="encryption-and-network-security"></a><span data-ttu-id="2f6a7-103">Verschlüsselung und Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="2f6a7-103">Encryption and network security</span></span>

<span data-ttu-id="2f6a7-104">Das Netzwerk Sicherheitsmodell für Windows Communication Foundation (WCF) ist umfangreich und komplex.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-104">The network security model for Windows Communication Foundation (WCF) is extensive and complex.</span></span> <span data-ttu-id="2f6a7-105">Sie beinhaltet Sicherheit auf Transport Ebene mithilfe von HTTPS oder TLS-over-TCP und Sicherheit auf Nachrichten Ebene, indem die WS-Security-Spezifikation zum Verschlüsseln einzelner Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-105">It includes transport-level security by using HTTPS or TLS-over-TCP, and message-level security by using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="2f6a7-106">GrpC verlässt sicheres Netzwerk auf das zugrunde liegende http/2-Protokoll, das Sie mithilfe von TLS-Zertifikaten sichern können.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-106">gRPC leaves secure networking to the underlying HTTP/2 protocol, which you can secure by using TLS certificates.</span></span>

<span data-ttu-id="2f6a7-107">Webbrowser sind auf die Verwendung von TLS-Verbindungen für http/2, aber die meisten programmgesteuerten Clients, einschließlich. NET-`HttpClient`, kann http/2 über unverschlüsselte Verbindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-107">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="2f6a7-108">`HttpClient` erfordert standardmäßig eine Verschlüsselung, Sie können diese jedoch überschreiben, indem Sie einen <xref:System.AppContext>-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-108">`HttpClient` does require encryption by default, but you can override this by using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="2f6a7-109">Für öffentliche APIs sollten Sie immer TLS-Verbindungen verwenden und gültige Zertifikate für ihre Dienste von einer richtigen SSL-Zertifizierungsstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-109">For public APIs, you should always use TLS connections, and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="2f6a7-110">[Letsencrypt](https://letsencrypt.org) bietet kostenlose, automatisierte SSL-Zertifikate, und die meisten Hostinginfrastrukturen unterstützen den letsencrypt-Standard mit gängigen Plug-ins oder Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-110">[LetsEncrypt](https://letsencrypt.org) provides free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="2f6a7-111">Für interne Dienste in einem Unternehmensnetzwerk sollten Sie weiterhin TLS verwenden, um den Netzwerk Datenverkehr zu und von ihren GrpC-Diensten zu sichern.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-111">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="2f6a7-112">Wenn Sie explizites TLS zwischen Diensten verwenden müssen, die in Kubernetes ausgeführt werden, sollten Sie eine in-Cluster-Zertifizierungsstelle und einen Zertifikat-Manager-Controller wie [Cert-Manager](https://docs.cert-manager.io/en/latest/)verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-112">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster certificate authority and a certificate manager controller like [cert-manager](https://docs.cert-manager.io/en/latest/).</span></span> <span data-ttu-id="2f6a7-113">Anschließend können Sie den Diensten zum Zeitpunkt der Bereitstellung automatisch Zertifikate zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2f6a7-113">You can then automatically assign certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2f6a7-114">[Zurück](channel-credentials.md)
>[Weiter](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="2f6a7-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
