---
title: 'Verschlüsselung und Netzwerksicherheit: GrpC für WCF-Entwickler'
description: Hinweise zur Netzwerksicherheit und-Verschlüsselung in GrpC
ms.date: 09/02/2019
ms.openlocfilehash: fd993a2d75e97011c6c92cee02c24c5358a211ad
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967780"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="1087a-103">Verschlüsselung und Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="1087a-103">Encryption and network security</span></span>

<span data-ttu-id="1087a-104">Das Netzwerk Sicherheitsmodell von WCF ist umfangreich und komplex, einschließlich Sicherheit auf Transport Ebene mithilfe von HTTPS oder TLS-over-TCP und Sicherheit auf Nachrichten Ebene mithilfe der WS-Security-Spezifikation zum Verschlüsseln einzelner Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="1087a-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="1087a-105">GrpC verlässt sicheres Netzwerk auf das zugrunde liegende http/2-Protokoll, das mithilfe regulärer TLS-Zertifikate geschützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1087a-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="1087a-106">Webbrowser sind auf die Verwendung von TLS-Verbindungen für http/2, aber die meisten programmgesteuerten Clients, einschließlich. NET-`HttpClient`, kann http/2 über unverschlüsselte Verbindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1087a-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="1087a-107">`HttpClient` *erfordert* standardmäßig eine Verschlüsselung, aber Sie können dies mithilfe eines <xref:System.AppContext> Schalters außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="1087a-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="1087a-108">Für öffentliche APIs sollten Sie immer TLS-Verbindungen verwenden und gültige Zertifikate für ihre Dienste von einer richtigen SSL-Zertifizierungsstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1087a-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="1087a-109">[Letsencrypt](https://letsencrypt.org) bietet kostenlose, automatisierte SSL-Zertifikate, und die meisten Hostinginfrastrukturen unterstützen den letsencrypt-Standard mit gängigen Plug-ins oder Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="1087a-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="1087a-110">Für interne Dienste in einem Unternehmensnetzwerk sollten Sie weiterhin TLS verwenden, um den Netzwerk Datenverkehr zu und von ihren GrpC-Diensten zu sichern.</span><span class="sxs-lookup"><span data-stu-id="1087a-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="1087a-111">Die Kommunikation zwischen den-Diensten in einem Cluster wie Kubernetes oder docker Swarm wird im allgemeinen automatisch von der Netzwerkebene des Containers verschlüsselt, sodass die Implementierung von TLS in Diensten, die ausschließlich in einem solchen Cluster ausgeführt werden, nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1087a-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="1087a-112">Weitere Informationen zu diesem Thema finden Sie im Abschnitt "Service Mesh" des nächsten Kapitels.</span><span class="sxs-lookup"><span data-stu-id="1087a-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="1087a-113">Wenn Sie explizites TLS zwischen Diensten verwenden müssen, die in Kubernetes ausgeführt werden, sollten Sie die Verwendung einer in-Cluster-Zertifizierungsstelle und eines Zertifikat-Manager-Controllers wie [Cert-Manager](https://docs.cert-manager.io/en/latest/) in Erwägung gezogen werden, um Dienste zum Zeitpunkt der Bereitstellung automatisch</span><span class="sxs-lookup"><span data-stu-id="1087a-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1087a-114">[Zurück](channel-credentials.md)
>[Weiter](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="1087a-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
