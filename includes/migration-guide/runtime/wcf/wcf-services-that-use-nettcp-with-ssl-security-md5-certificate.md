---
ms.openlocfilehash: afcb9b950d4c47b4251dcc8ab0cf9cfc702005c8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497287"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="0c372-101">WCF-Dienste, die NETTCP mit SSL-Sicherheit und MD5-Zertifikatauthentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c372-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="0c372-102">Details</span><span class="sxs-lookup"><span data-stu-id="0c372-102">Details</span></span>

<span data-ttu-id="0c372-103">.NET Framework 4.6 fügt TLS 1.1 und TLS 1.2 zur WCF-SSL-Standardprotokolliste hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c372-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="0c372-104">Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet. TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht.</span><span class="sxs-lookup"><span data-stu-id="0c372-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="0c372-105">Wenn ein Kunde daher ein MD5-Zertifikat verwendet, kann der WCF-Client keine Verbindung mit dem WCF-Dienst herstellen.</span><span class="sxs-lookup"><span data-stu-id="0c372-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c372-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0c372-106">Suggestion</span></span>

<span data-ttu-id="0c372-107">Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="0c372-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="0c372-108">Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c372-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="0c372-109">Dies ist die empfohlene Lösung.</span><span class="sxs-lookup"><span data-stu-id="0c372-109">This is the recommended solution.</span></span>
- <span data-ttu-id="0c372-110">Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="0c372-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="0c372-111">Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c372-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="0c372-112">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="0c372-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="0c372-113">In der folgenden Konfigurationsdatei wird so vorgegangen:</span><span class="sxs-lookup"><span data-stu-id="0c372-113">The following configuration file does this:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- <span data-ttu-id="0c372-114">Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) oder einer früheren Version des Protokolls im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="0c372-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="0c372-115">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="0c372-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="0c372-116">name</span><span class="sxs-lookup"><span data-stu-id="0c372-116">Name</span></span>    | <span data-ttu-id="0c372-117">Wert</span><span class="sxs-lookup"><span data-stu-id="0c372-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="0c372-118">Bereich</span><span class="sxs-lookup"><span data-stu-id="0c372-118">Scope</span></span>   | <span data-ttu-id="0c372-119">Gering</span><span class="sxs-lookup"><span data-stu-id="0c372-119">Minor</span></span>   |
| <span data-ttu-id="0c372-120">Version</span><span class="sxs-lookup"><span data-stu-id="0c372-120">Version</span></span> | <span data-ttu-id="0c372-121">4.6</span><span class="sxs-lookup"><span data-stu-id="0c372-121">4.6</span></span>     |
| <span data-ttu-id="0c372-122">Typ</span><span class="sxs-lookup"><span data-stu-id="0c372-122">Type</span></span>    | <span data-ttu-id="0c372-123">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0c372-123">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="0c372-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0c372-124">Affected APIs</span></span>

<span data-ttu-id="0c372-125">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="0c372-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
