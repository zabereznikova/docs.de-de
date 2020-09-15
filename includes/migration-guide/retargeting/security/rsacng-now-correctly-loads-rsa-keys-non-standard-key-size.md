---
ms.openlocfilehash: c1e85941c8c6c31c7d937d0671ad955fa6490783
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614439"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng lädt nun fehlerfrei RSA-Schlüssel, die nicht der Standardschlüsselgröße entsprechen

#### <a name="details"></a>Details

In .NET Framework-Versionen, die älter sind als Version 4.6.2, können Kunden, die keine Standardschlüsselgrößen für RSA-Zertifikate verwenden, auf diese Schlüssel nicht über die Erweiterungsmethoden <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> und <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> zugreifen.  Eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> wird mit der Meldung &quot;The requested key size is not supported&quot; (Die angeforderte Schlüsselgröße wird nicht unterstützt.) ausgelöst. Dieses Problem wurde in .NET Framework 4.6.2 behoben. Ebenso funktionieren <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> und <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> nun mit Schlüsselgrößen, die nicht der Standardgröße entsprechen, ohne dass eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> ausgelöst wird.

#### <a name="suggestion"></a>Vorschlag

Wenn eine Ausnahmebehandlungslogik auf dem vorherigen Verhalten basiert, durch das eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> ausgelöst wird, sobald eine von der Standardgröße abweichende Schlüsselgröße verwendet wird, kann das Entfernen der Logik sinnvoll sein.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
