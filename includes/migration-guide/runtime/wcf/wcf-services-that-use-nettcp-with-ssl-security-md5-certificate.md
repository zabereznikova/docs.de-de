---
ms.openlocfilehash: afcb9b950d4c47b4251dcc8ab0cf9cfc702005c8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497287"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a>WCF-Dienste, die NETTCP mit SSL-Sicherheit und MD5-Zertifikatauthentifizierung verwenden

#### <a name="details"></a>Details

.NET Framework 4.6 fügt TLS 1.1 und TLS 1.2 zur WCF-SSL-Standardprotokolliste hinzu. Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet. TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht. Wenn ein Kunde daher ein MD5-Zertifikat verwendet, kann der WCF-Client keine Verbindung mit dem WCF-Dienst herstellen.

#### <a name="suggestion"></a>Vorschlag

Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:

- Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird. Dies ist die empfohlene Lösung.
- Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls. Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.

> [!WARNING]
> Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.

In der folgenden Konfigurationsdatei wird so vorgegangen:

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

- Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) oder einer früheren Version des Protokolls im Quellcode.

> [!WARNING]
> Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.

| name    | Wert   |
|:--------|:--------|
| Bereich   | Gering   |
| Version | 4.6     |
| Typ    | Laufzeit |

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
