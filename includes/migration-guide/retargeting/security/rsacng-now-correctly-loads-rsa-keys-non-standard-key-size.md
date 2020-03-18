---
ms.openlocfilehash: 4892f75e4ae673d9d9cc7e9eeb6fb9b1a73f572e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859242"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng lädt nun fehlerfrei RSA-Schlüssel, die nicht der Standardschlüsselgröße entsprechen

|   |   |
|---|---|
|Details|In .NET Framework-Versionen, die älter sind als Version 4.6.2, können Kunden, die keine Standardschlüsselgrößen für RSA-Zertifikate verwenden, auf diese Schlüssel nicht über die Erweiterungsmethoden <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> und <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> zugreifen.  Eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> wird mit der Meldung &quot;The requested key size is not supported&quot; (Die angeforderte Schlüsselgröße wird nicht unterstützt.) ausgelöst. Dieses Problem wurde in .NET Framework 4.6.2 behoben. Ebenso funktionieren <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> und <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> nun mit Schlüsselgrößen, die nicht der Standardgröße entsprechen, ohne dass eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> ausgelöst wird.|
|Vorschlag|Wenn eine Ausnahmebehandlungslogik auf dem vorherigen Verhalten basiert, durch das eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> ausgelöst wird, sobald eine von der Standardgröße abweichende Schlüsselgröße verwendet wird, kann das Entfernen der Logik sinnvoll sein.|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
